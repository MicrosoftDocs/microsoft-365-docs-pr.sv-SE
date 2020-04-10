---
title: Ändra namnservrar för att konfigurera Office 365 med AWS (Amazon Web Services)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Lär dig hur du kan konfigurera Office 365 för att hantera dina DNS-poster på Amazon Web Services (AWS). '
ms.openlocfilehash: a7125cf0add8200fe152c426f47e7f27a8f6226c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212359"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="35f4c-103">Ändra namnservrar för att konfigurera Office 365 med AWS (Amazon Web Services)</span><span class="sxs-lookup"><span data-stu-id="35f4c-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="35f4c-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="35f4c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="35f4c-p101">Följ instruktionerna nedan om du vill att Office 365-DNS-posterna ska hanteras i Office 365. (Om du föredrar, kan du [hantera alla Office 365 DNS-poster hos AWS](create-dns-records-at-aws.md).)</span><span class="sxs-lookup"><span data-stu-id="35f4c-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="35f4c-107">Lägga till en TXT-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="35f4c-107">Add a TXT record for verification</span></span>

<span data-ttu-id="35f4c-p102">Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="35f4c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35f4c-p103">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="35f4c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="35f4c-p104">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="35f4c-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="35f4c-114">På sidan **Resurser** väljer du **Värdzoner**.</span><span class="sxs-lookup"><span data-stu-id="35f4c-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="35f4c-115">Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.**</span><span class="sxs-lookup"><span data-stu-id="35f4c-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="35f4c-116">Välj **Skapa postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="35f4c-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="35f4c-117">I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="35f4c-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="35f4c-118">(Välj värdena för **Type** och **Routing Policy** i listrutorna.)</span><span class="sxs-lookup"><span data-stu-id="35f4c-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="35f4c-p105">Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="35f4c-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35f4c-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="35f4c-121">**Name**</span></span> <br/> |<span data-ttu-id="35f4c-122">**Type (Typ)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-122">**Type**</span></span> <br/> |<span data-ttu-id="35f4c-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="35f4c-123">**Alias**</span></span> <br/> |<span data-ttu-id="35f4c-124">**TTL (sekunder)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="35f4c-125">**Värde**</span><span class="sxs-lookup"><span data-stu-id="35f4c-125">**Value**</span></span> <br/> |<span data-ttu-id="35f4c-126">**Routing Policy (Routningsprincip)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="35f4c-127">(Lämna det här fältet tomt)</span><span class="sxs-lookup"><span data-stu-id="35f4c-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="35f4c-128">TXT - text</span><span class="sxs-lookup"><span data-stu-id="35f4c-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="35f4c-129">Nej</span><span class="sxs-lookup"><span data-stu-id="35f4c-129">No</span></span>  <br/> |<span data-ttu-id="35f4c-130">300</span><span class="sxs-lookup"><span data-stu-id="35f4c-130">300</span></span>  <br/> |<span data-ttu-id="35f4c-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="35f4c-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="35f4c-132">**Obs!** Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="35f4c-132">**Note:** This is an example.</span></span> <span data-ttu-id="35f4c-133">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="35f4c-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="35f4c-134">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="35f4c-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="35f4c-135">Enkelt</span><span class="sxs-lookup"><span data-stu-id="35f4c-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="35f4c-136">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="35f4c-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="35f4c-137">Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="35f4c-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="35f4c-138">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="35f4c-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="35f4c-139">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="35f4c-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="35f4c-140">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="35f4c-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="35f4c-141">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="35f4c-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="35f4c-142">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="35f4c-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="35f4c-143">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="35f4c-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="35f4c-p107">Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="35f4c-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="35f4c-147">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="35f4c-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="35f4c-p108">Om du vill slutföra konfigurationen av domänen med Office 365 kan du ändra domänens NS-poster hos domänregistratorn så att de pekar på de primära och sekundära namnservrarna i Office 365. Då ställs Office 365 in så att domänens DNS-poster uppdateras. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.</span><span class="sxs-lookup"><span data-stu-id="35f4c-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="35f4c-p109">Om du ändrar domänens NS-poster så att de pekar på Office 365-namnservrarna påverkas alla tjänster som är kopplade till domänen. Till exempel kommer all e-post som skickas till din domän (till exempel rob@ *your_domain*  .com) till Office 365 när du har gjort den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="35f4c-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="35f4c-p110">Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. >  När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="35f4c-p110">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="35f4c-155">Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="35f4c-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="35f4c-156">Du uppmanas att logga in först.</span><span class="sxs-lookup"><span data-stu-id="35f4c-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="35f4c-157">På sidan **Resurser** väljer du **Värdzoner**.</span><span class="sxs-lookup"><span data-stu-id="35f4c-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="35f4c-158">Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.**</span><span class="sxs-lookup"><span data-stu-id="35f4c-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="35f4c-159">Välj undergruppen **Nameserver**.</span><span class="sxs-lookup"><span data-stu-id="35f4c-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="35f4c-161">I **NS - Name server**-undergruppen, i **Value**, tar du bort alla namnservrar genom att markera dem alla och sedan trycka på **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="35f4c-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="35f4c-162">Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="35f4c-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="35f4c-163">(Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="35f4c-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="35f4c-165">I **området TTL (Sekunder):** väljer du **1h** (1 timme).</span><span class="sxs-lookup"><span data-stu-id="35f4c-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Välj 1H i en timme](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="35f4c-167">Fortfarande i **NS - Name server**-undergruppen och i värderutan **Value**: Skriv eller kopiera och klistra in värdet för första raden - **First line** - från tabellen nedan. Tryck på **Retur** på tangentbordet och skriv eller kopiera och klistra in värdet för nästa **rad**.</span><span class="sxs-lookup"><span data-stu-id="35f4c-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="35f4c-168">Varje namnservervärde  *måste*  stå på en egen rad i värderutan: **Value**. Se bildförklaringen nedan.</span><span class="sxs-lookup"><span data-stu-id="35f4c-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="35f4c-169">**Första raden (First line)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-169">**First line**</span></span> <br/> |<span data-ttu-id="35f4c-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="35f4c-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="35f4c-171">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="35f4c-172">**Andra raden (Second line)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-172">**Second line**</span></span> <br/> |<span data-ttu-id="35f4c-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="35f4c-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="35f4c-174">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="35f4c-175">**Tredje raden (Third line)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-175">**Third line**</span></span> <br/> |<span data-ttu-id="35f4c-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="35f4c-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="35f4c-177">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="35f4c-178">**Fjärde raden (Fourth line)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="35f4c-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="35f4c-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="35f4c-180">**Värdet MÅSTE sluta med en punkt (.)**</span><span class="sxs-lookup"><span data-stu-id="35f4c-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Skriva eller klistra in värdet för första raden i rutan Värde](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="35f4c-182">Välj **Spara postuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="35f4c-182">Select **Save Record Set**.</span></span>
    
    ![Välj Spara postuppsättning](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="35f4c-p113">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="35f4c-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
