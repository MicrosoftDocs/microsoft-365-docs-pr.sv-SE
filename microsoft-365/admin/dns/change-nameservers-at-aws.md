---
title: Ändra namnservrar för att konfigurera Microsoft med Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Lär dig hur du kan konfigurera Microsoft för att hantera dina DNS-poster på Amazon Web Services (AWS). '
ms.openlocfilehash: 6efe06400652783ffbc6732b5c6327067c5c484c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400683"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="31e9a-103">Ändra namnservrar för att konfigurera Microsoft med Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="31e9a-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="31e9a-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="31e9a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="31e9a-105">Följ dessa instruktioner om du vill att Microsoft ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="31e9a-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="31e9a-106">(Om du vill kan du [hantera alla dina Microsoft DNS-poster på AWS](create-dns-records-at-aws.md).)</span><span class="sxs-lookup"><span data-stu-id="31e9a-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="31e9a-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="31e9a-107">Add a TXT record for verification</span></span>

<span data-ttu-id="31e9a-p102">Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="31e9a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="31e9a-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="31e9a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="31e9a-p104">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="31e9a-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="31e9a-114">På sidan **Resurser** väljer du **Värdzoner**.</span><span class="sxs-lookup"><span data-stu-id="31e9a-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="31e9a-115">Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.**</span><span class="sxs-lookup"><span data-stu-id="31e9a-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="31e9a-116">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="31e9a-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="31e9a-117">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="31e9a-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="31e9a-118">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="31e9a-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="31e9a-p105">Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="31e9a-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="31e9a-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="31e9a-121">**Name**</span></span> <br/> |<span data-ttu-id="31e9a-122">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-122">**Type**</span></span> <br/> |<span data-ttu-id="31e9a-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="31e9a-123">**Alias**</span></span> <br/> |<span data-ttu-id="31e9a-124">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="31e9a-125">**Värde**</span><span class="sxs-lookup"><span data-stu-id="31e9a-125">**Value**</span></span> <br/> |<span data-ttu-id="31e9a-126">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="31e9a-127">(Lämna det här fältet tomt)</span><span class="sxs-lookup"><span data-stu-id="31e9a-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="31e9a-128">TXT - text</span><span class="sxs-lookup"><span data-stu-id="31e9a-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="31e9a-129">Nej</span><span class="sxs-lookup"><span data-stu-id="31e9a-129">No</span></span>  <br/> |<span data-ttu-id="31e9a-130">300</span><span class="sxs-lookup"><span data-stu-id="31e9a-130">300</span></span>  <br/> |<span data-ttu-id="31e9a-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="31e9a-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="31e9a-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="31e9a-132">**Note:** This is an example.</span></span> <span data-ttu-id="31e9a-133">Använd ditt specifika \*\*Mål eller pekar på adress \*\* värde här, från tabellen.</span><span class="sxs-lookup"><span data-stu-id="31e9a-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="31e9a-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="31e9a-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="31e9a-135">Enkelt</span><span class="sxs-lookup"><span data-stu-id="31e9a-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="31e9a-136">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="31e9a-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="31e9a-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="31e9a-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="31e9a-138">Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär en sökning efter posten.</span><span class="sxs-lookup"><span data-stu-id="31e9a-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="31e9a-139">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="31e9a-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="31e9a-140">I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.</span><span class="sxs-lookup"><span data-stu-id="31e9a-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="31e9a-141">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="31e9a-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="31e9a-142">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="31e9a-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="31e9a-143">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="31e9a-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="31e9a-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="31e9a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="31e9a-147">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="31e9a-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="31e9a-148">Om du vill slutföra inrättandet av domänen med Microsoft ändrar du domänens NS-poster på domänregistraren så att de pekar på Microsofts primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="31e9a-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="31e9a-149">Detta ställer in Microsoft för att uppdatera domänens DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="31e9a-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="31e9a-150">Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="31e9a-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="31e9a-151">När du ändrar domänens NS-poster så att de pekar på Microsofts namnservrar påverkas alla tjänster som för närvarande är associerade med domänen.</span><span class="sxs-lookup"><span data-stu-id="31e9a-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="31e9a-152">Till exempel börjar all e-post som skickas till din domän (t.ex. *rob@ your_domain* .com) komma till Microsoft när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="31e9a-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="31e9a-p110">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. >  När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="31e9a-p110">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="31e9a-155">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="31e9a-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="31e9a-156">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="31e9a-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="31e9a-157">På sidan **Resurser** väljer du **Värdzoner**.</span><span class="sxs-lookup"><span data-stu-id="31e9a-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="31e9a-158">Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.**</span><span class="sxs-lookup"><span data-stu-id="31e9a-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="31e9a-159">Välj undergruppen **Nameserver**.</span><span class="sxs-lookup"><span data-stu-id="31e9a-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="31e9a-161">I **NS - Name server**-undergruppen, i **Value**, tar du bort alla namnservrar genom att markera dem alla och sedan trycka på **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="31e9a-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="31e9a-162">Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="31e9a-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="31e9a-163">(Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="31e9a-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="31e9a-165">I **området TTL (Sekunder):** väljer du **1h** (1 timme).</span><span class="sxs-lookup"><span data-stu-id="31e9a-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Välj 1H i en timme](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="31e9a-167">Fortfarande i **NS - Name server**-undergruppen och i värderutan **Value**: Skriv eller kopiera och klistra in värdet för första raden - **First line** - från tabellen nedan. Tryck på **Retur** på tangentbordet och skriv eller kopiera och klistra in värdet för nästa **rad**.</span><span class="sxs-lookup"><span data-stu-id="31e9a-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="31e9a-168">Varje namnservervärde  *måste*  stå på en egen rad i värderutan: **Value**. Se bildförklaringen nedan.</span><span class="sxs-lookup"><span data-stu-id="31e9a-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="31e9a-169">**Första raden (First line)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-169">**First line**</span></span> <br/> |<span data-ttu-id="31e9a-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="31e9a-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="31e9a-171">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="31e9a-172">**Andra raden (Second line)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-172">**Second line**</span></span> <br/> |<span data-ttu-id="31e9a-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="31e9a-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="31e9a-174">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="31e9a-175">**Tredje raden (Third line)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-175">**Third line**</span></span> <br/> |<span data-ttu-id="31e9a-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="31e9a-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="31e9a-177">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="31e9a-178">**Fjärde raden (Fourth line)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="31e9a-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="31e9a-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="31e9a-180">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="31e9a-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Skriva eller klistra in värdet för första raden i rutan Värde](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="31e9a-182">Välj **Spara postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="31e9a-182">Select **Save Record Set**.</span></span>
    
    ![Välj Spara postuppsättning](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="31e9a-184">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="31e9a-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="31e9a-185">Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="31e9a-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
