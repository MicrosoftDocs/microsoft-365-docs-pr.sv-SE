---
title: Ändra namnservrar för att konfigurera Microsoft med Network Solutions
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Lär dig att konfigurera din anpassade Microsoft-domän med Network Solutions om du vill att Microsoft ska hantera dina DNS-poster. '
ms.openlocfilehash: 2b3b575943ebd95ffcbd34dd4578133fa7dd4f79
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629761"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="1a412-103">Ändra namnservrar för att konfigurera Microsoft med Network Solutions</span><span class="sxs-lookup"><span data-stu-id="1a412-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="1a412-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="1a412-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="1a412-105">Följ dessa instruktioner om du vill att Microsoft ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="1a412-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="1a412-106">(Om du vill kan du [hantera alla Microsoft DNS-poster på Network Solutions](create-dns-records-at-network-solutions.md).)</span><span class="sxs-lookup"><span data-stu-id="1a412-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="1a412-107">Lägga till en TXT-post på Network Solutions för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="1a412-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="1a412-108">Innan du använder domänen med Microsoft måste vi se till att du äger den.</span><span class="sxs-lookup"><span data-stu-id="1a412-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="1a412-109">Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="1a412-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a412-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="1a412-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="1a412-112">Följ stegen nedan eller [titta på videon (börja vid 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1a412-112">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="1a412-p104">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="1a412-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1a412-115">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="1a412-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="1a412-117">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="1a412-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="1a412-119">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="1a412-119">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="1a412-121">Välj **Hantera avancerade DNS-poster**.</span><span class="sxs-lookup"><span data-stu-id="1a412-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="1a412-122">(Du kan behöva rulla nedåt.)</span><span class="sxs-lookup"><span data-stu-id="1a412-122">(You may have to scroll down.)</span></span>
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="1a412-124">Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Redigera TXT-poster**.</span><span class="sxs-lookup"><span data-stu-id="1a412-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Välj Redigera TXT-poster](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="1a412-126">I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1a412-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="1a412-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="1a412-127">**Host**</span></span>|<span data-ttu-id="1a412-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1a412-128">**TTL**</span></span>|<span data-ttu-id="1a412-129">**Text**</span><span class="sxs-lookup"><span data-stu-id="1a412-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="1a412-130">(Värdet ändras till **@ (None)** när du sparar posten.)</span><span class="sxs-lookup"><span data-stu-id="1a412-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="1a412-131">3600</span><span class="sxs-lookup"><span data-stu-id="1a412-131">3600</span></span>  <br/> |<span data-ttu-id="1a412-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1a412-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1a412-133">**Obs:** Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="1a412-133">**Note**: This is an example.</span></span> <span data-ttu-id="1a412-134">Använd ditt specifika **mål- eller poäng till-adress-värde** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a412-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="1a412-135">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="1a412-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Skriva eller klistra in värden i rutorna för den nya posten](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="1a412-137">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="1a412-137">Select **Continue**.</span></span>
    
    ![Välj Fortsätt](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="1a412-139">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="1a412-139">Select **Save Changes**.</span></span>
    
    ![Välj Spara ändringar](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="1a412-141">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="1a412-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1a412-142">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 ska söka efter posten.</span><span class="sxs-lookup"><span data-stu-id="1a412-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="1a412-143">När Microsoft hittar rätt TXT-post verifieras domänen.</span><span class="sxs-lookup"><span data-stu-id="1a412-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1a412-144">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a></span><span class="sxs-lookup"><span data-stu-id="1a412-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1a412-145">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="1a412-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1a412-146">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="1a412-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1a412-147">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="1a412-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1a412-p106">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1a412-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="1a412-151">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="1a412-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="1a412-152">Om du vill slutföra inrättandet av domänen med Microsoft ändrar du domänens NS-poster på domänregistraren så att de pekar på Microsofts primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="1a412-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="1a412-153">Detta ställer in Microsoft för att uppdatera domänens DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="1a412-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="1a412-154">Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="1a412-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1a412-155">När du ändrar domänens NS-poster så att de pekar på Microsofts namnservrar påverkas alla tjänster som för närvarande är associerade med domänen.</span><span class="sxs-lookup"><span data-stu-id="1a412-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="1a412-156">Till exempel börjar all e-post som skickas till din domän (t.ex. *rob@ your_domain* .com) komma till Microsoft när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="1a412-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="1a412-157">Är du redo att ändra dina NS-poster så att Microsoft kan konfigurera din domän?</span><span class="sxs-lookup"><span data-stu-id="1a412-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="1a412-158">Följ stegen nedan eller [titta på videon (börja vid 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="1a412-158">Follow the steps below or [watch the video (start at 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="1a412-159">När du har slutfört stegen i det här avsnittet är de *enda* namnservrarna som ska visas dessa fyra: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**och **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="1a412-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="1a412-160">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till  *korrekta*  namnservrar om de inte redan finns i listan.</span><span class="sxs-lookup"><span data-stu-id="1a412-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="1a412-161">Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="1a412-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="1a412-162">Du uppmanas att logga in.</span><span class="sxs-lookup"><span data-stu-id="1a412-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1a412-163">Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .</span><span class="sxs-lookup"><span data-stu-id="1a412-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="1a412-165">Markera kryssrutan bredvid namnet på den domän som du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="1a412-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="1a412-167">Välj **Redigera DNS**.</span><span class="sxs-lookup"><span data-stu-id="1a412-167">Select **Edit DNS**.</span></span>
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="1a412-169">Välj **Flytta DNS**.</span><span class="sxs-lookup"><span data-stu-id="1a412-169">Select **Move DNS**.</span></span>
    
    ![NätverkLösningarBP-Redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="1a412-171">Beroende på om det redan finns namnservrar listade på sidan som visas nu, fortsätter du till en av följande procedurer:</span><span class="sxs-lookup"><span data-stu-id="1a412-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="1a412-172">Om **INGA** namnservrar visas [Om INGA namnservrar visas](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="1a412-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="1a412-173">Om det redan **FINNS** namnservrar listade [Om det redan FINNS namnservrar listade](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="1a412-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="1a412-174">Om INGA namnservrar visas</span><span class="sxs-lookup"><span data-stu-id="1a412-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="1a412-175">Välj **Lägg till fler namnservrar**i avsnittet Ange **domännamnsservrar** på sidan **Domäner** .</span><span class="sxs-lookup"><span data-stu-id="1a412-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NätverkLösningarBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="1a412-177">På sidan **Domain Names** skriver eller kopierar och klistrar du in namnservervärdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1a412-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="1a412-178">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="1a412-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="1a412-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1a412-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1a412-180">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="1a412-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="1a412-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1a412-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1a412-182">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="1a412-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="1a412-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1a412-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1a412-184">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="1a412-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="1a412-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1a412-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NätverkLösningarBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="1a412-187">Välj **Flytta DNS**.</span><span class="sxs-lookup"><span data-stu-id="1a412-187">Select **Move DNS**.</span></span>
    
    ![NätverkLösningarBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="1a412-189">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="1a412-189">Select **Save Changes**.</span></span>
    
    ![NätverkLösningarBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="1a412-191">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="1a412-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="1a412-192">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="1a412-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="1a412-193">Om det redan FINNS namnservrar listade</span><span class="sxs-lookup"><span data-stu-id="1a412-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="1a412-p113">Följ de här anvisningarna  *endast*  om det finns andra namnservrar utöver de fyra  *korrekta*  namnservrarna. (Ta alltså  *endast*  bort eventuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="1a412-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="1a412-196">Om det finns andra namnservrar tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten.</span><span class="sxs-lookup"><span data-stu-id="1a412-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NätverkLösningar-BP-Redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="1a412-198">Välj **Lägg till fler namnservrar**.</span><span class="sxs-lookup"><span data-stu-id="1a412-198">Select **Add More Name Servers**.</span></span>
    
    ![NätverkLösningarBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="1a412-200">På sidan **Domain Names** skriver eller kopierar och klistrar du in namnservervärdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1a412-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="1a412-201">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="1a412-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="1a412-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1a412-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1a412-203">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="1a412-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="1a412-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1a412-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1a412-205">**Name Server 3**</span><span class="sxs-lookup"><span data-stu-id="1a412-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="1a412-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1a412-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="1a412-207">**Name Server 4**</span><span class="sxs-lookup"><span data-stu-id="1a412-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="1a412-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="1a412-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NätverkLösningarBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="1a412-210">Välj **Flytta DNS**.</span><span class="sxs-lookup"><span data-stu-id="1a412-210">Select **Move DNS**.</span></span>
    
    ![NätverkLösningarBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="1a412-212">Välj **Spara ändringar.**</span><span class="sxs-lookup"><span data-stu-id="1a412-212">Select **Save Changes.**</span></span>
    
    ![NätverkLösningarBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="1a412-214">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="1a412-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="1a412-215">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="1a412-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
