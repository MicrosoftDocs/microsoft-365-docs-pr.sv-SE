---
title: Ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Lär dig att lägga till och konfigurera din domän i Microsoft 365 så att tjänster som e-post och Skype för företag Online använder ditt eget domännamn.
ms.openlocfilehash: 7f1ade6cb3013126fb011fe9232b3b4c2e9a82d4
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683133"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="76a2f-103">Ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator</span><span class="sxs-lookup"><span data-stu-id="76a2f-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="76a2f-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="76a2f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="76a2f-105">Följ de här anvisningarna för att lägga till och konfigurera din domän i Microsoft 365 så att tjänster som e-post och Teams använder ditt eget domännamn.</span><span class="sxs-lookup"><span data-stu-id="76a2f-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="76a2f-106">Det gör du genom att verifiera domänen och sedan ändra domänens namnservrar till Microsoft 365 så att rätt DNS-poster kan ställas in åt dig.</span><span class="sxs-lookup"><span data-stu-id="76a2f-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="76a2f-107">Följ de här anvisningarna om följande påståenden beskriver din situation:</span><span class="sxs-lookup"><span data-stu-id="76a2f-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="76a2f-108">Du har en egen domän och vill konfigurera den så att den fungerar med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76a2f-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="76a2f-109">Du vill Microsoft 365 att hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="76a2f-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="76a2f-110">(Du kan även välja att [hantera DNS-posterna själv](../setup/add-domain.md).)</span><span class="sxs-lookup"><span data-stu-id="76a2f-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="76a2f-111">Lägga till en TXT- eller MX-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="76a2f-111">Add a TXT or MX record for verification</span></span>

> [!NOTE]
> <span data-ttu-id="76a2f-p103">Du skapar bara en av dessa poster. TXT är den vanligaste posttypen, men den stöds inte av vissa DNS-värdar. I sådana fall skapar du en MX-post istället.</span><span class="sxs-lookup"><span data-stu-id="76a2f-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="76a2f-p104">Innan du använder din domän med Microsoft 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="76a2f-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76a2f-p105">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="76a2f-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="76a2f-118">Ta reda på var på din DNS-värds webbplats som du kan skapa en ny post</span><span class="sxs-lookup"><span data-stu-id="76a2f-118">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="76a2f-119">Logga in på din DNS-värds webbplats.</span><span class="sxs-lookup"><span data-stu-id="76a2f-119">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="76a2f-120">Välj din domän.</span><span class="sxs-lookup"><span data-stu-id="76a2f-120">Choose your domain.</span></span>
    
3. <span data-ttu-id="76a2f-121">Gå till den sida där du kan redigera DNS-poster för din domän.</span><span class="sxs-lookup"><span data-stu-id="76a2f-121">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="76a2f-122">Skapa posten</span><span class="sxs-lookup"><span data-stu-id="76a2f-122">Create the record</span></span>

<span data-ttu-id="76a2f-123">Beroende på om du skapar en TXT-post eller en MX-post gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="76a2f-123">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="76a2f-124">**Om du skapar en TXT-post använder du följande värden:**</span><span class="sxs-lookup"><span data-stu-id="76a2f-124">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76a2f-125">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="76a2f-125">**Record Type**</span></span> <br/> |<span data-ttu-id="76a2f-126">**Alias** eller **Host Name**</span><span class="sxs-lookup"><span data-stu-id="76a2f-126">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="76a2f-127">**Värde**</span><span class="sxs-lookup"><span data-stu-id="76a2f-127">**Value**</span></span> <br/> |<span data-ttu-id="76a2f-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="76a2f-128">**TTL**</span></span> <br/> |
|<span data-ttu-id="76a2f-129">TXT</span><span class="sxs-lookup"><span data-stu-id="76a2f-129">TXT</span></span>  <br/> |<span data-ttu-id="76a2f-130">Gör något av följande: skriv **@**, lämna fältet tomt eller skriv domännamnet.</span><span class="sxs-lookup"><span data-stu-id="76a2f-130">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="76a2f-131">> [!NOTE]> Olika DNS-värdar har olika krav för det här fältet.</span><span class="sxs-lookup"><span data-stu-id="76a2f-131">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="76a2f-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="76a2f-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="76a2f-133">> [!NOTE]> Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="76a2f-133">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="76a2f-134">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76a2f-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="76a2f-135">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="76a2f-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="76a2f-136">Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.</span><span class="sxs-lookup"><span data-stu-id="76a2f-136">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="76a2f-137">**Om du skapar en MX-post ska du använda följande värden:**</span><span class="sxs-lookup"><span data-stu-id="76a2f-137">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76a2f-138">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="76a2f-138">**Record Type**</span></span>|<span data-ttu-id="76a2f-139">**Alias** eller **Host Name**</span><span class="sxs-lookup"><span data-stu-id="76a2f-139">**Alias** or **Host Name**</span></span>|<span data-ttu-id="76a2f-140">**Värde**</span><span class="sxs-lookup"><span data-stu-id="76a2f-140">**Value**</span></span>|<span data-ttu-id="76a2f-141">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="76a2f-141">**Priority**</span></span>|<span data-ttu-id="76a2f-142">**TTL**</span><span class="sxs-lookup"><span data-stu-id="76a2f-142">**TTL**</span></span>|
|<span data-ttu-id="76a2f-143">MX</span><span class="sxs-lookup"><span data-stu-id="76a2f-143">MX</span></span>|<span data-ttu-id="76a2f-144">Skriv antingen **@** eller domännamnet.</span><span class="sxs-lookup"><span data-stu-id="76a2f-144">Type either **@** or your domain name.</span></span> |<span data-ttu-id="76a2f-145">MS=ms *XXXXXXXX* > [!NOTE]> Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="76a2f-145">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="76a2f-146">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76a2f-146">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="76a2f-147">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="76a2f-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="76a2f-148">Under **Prioritet** anger du en lägre prioritet än den som eventuella befintliga MX-poster har, för att undvika konflikter med den MX-post som används för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="76a2f-148">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="76a2f-149">Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="76a2f-149">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="76a2f-150">Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.</span><span class="sxs-lookup"><span data-stu-id="76a2f-150">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="76a2f-151">Spara posten</span><span class="sxs-lookup"><span data-stu-id="76a2f-151">Save the record</span></span>

<span data-ttu-id="76a2f-152">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="76a2f-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="76a2f-153">När Microsoft 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="76a2f-153">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="76a2f-154">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="76a2f-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="76a2f-155">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="76a2f-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="76a2f-156">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-156">On the **Setup** page, select **Start setup**.</span></span>
 
  
4. <span data-ttu-id="76a2f-157">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-157">On the **Verify domain** page, select **Verify**.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="76a2f-p109">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="76a2f-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="76a2f-161">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="76a2f-161">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="76a2f-162">När du kommer till det sista steget i domäninstallationsguiden i Microsoft 365 har du en uppgift kvar.</span><span class="sxs-lookup"><span data-stu-id="76a2f-162">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="76a2f-163">Om du vill konfigurera domänen med Microsoft 365-tjänster som e-post kan du ändra domänens namnserverposter (eller NS-poster) hos domänregistratorn så att de pekar på Microsoft 365 primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="76a2f-163">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="76a2f-164">Eftersom DNS Microsoft 365 inte är värd för, konfigureras sedan de nödvändiga DNS-posterna för dina tjänster automatiskt.</span><span class="sxs-lookup"><span data-stu-id="76a2f-164">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="76a2f-165">Du kan uppdatera namnserverposterna själv genom att följa de steg som domänregistratorn tillhandahåller i hjälpavsnitten på sin webbplats (om det finns några).</span><span class="sxs-lookup"><span data-stu-id="76a2f-165">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="76a2f-166">Om du inte är bekant med DNS kontaktar du supporten hos domänregistratorn.</span><span class="sxs-lookup"><span data-stu-id="76a2f-166">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="76a2f-167">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="76a2f-167">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="76a2f-168">Leta reda på var på domänregistratorns webbplats som du kan ändra namnservrar för din domän eller ett område där du kan använda anpassade namnservrar.</span><span class="sxs-lookup"><span data-stu-id="76a2f-168">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="76a2f-169">Skapa namnserverposter eller redigera de befintliga namnserverposterna så att de matchar följande värden:</span><span class="sxs-lookup"><span data-stu-id="76a2f-169">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="76a2f-170">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="76a2f-170">First nameserver</span></span>  <br/> |<span data-ttu-id="76a2f-171">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="76a2f-171">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="76a2f-172">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="76a2f-172">Second nameserver</span></span>  <br/> |<span data-ttu-id="76a2f-173">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="76a2f-173">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="76a2f-174">Tredje namnserver</span><span class="sxs-lookup"><span data-stu-id="76a2f-174">Third nameserver</span></span>  <br/> |<span data-ttu-id="76a2f-175">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="76a2f-175">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="76a2f-176">Fjärde namnserver</span><span class="sxs-lookup"><span data-stu-id="76a2f-176">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="76a2f-177">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="76a2f-177">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="76a2f-178">Det är bäst att lägga till alla fyra posterna, men om din registrator bara har stöd för två lägger du **ns1.bdm.microsoftonline.com** och **ns2.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-178">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="76a2f-179">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="76a2f-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="76a2f-180">Om du ändrar domänens NS-poster så att de pekar Microsoft 365 namnservrarna påverkas alla tjänster som är kopplade till domänen.</span><span class="sxs-lookup"><span data-stu-id="76a2f-180">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="76a2f-181">Om du hoppade över något steg i guiden, t.ex.</span><span class="sxs-lookup"><span data-stu-id="76a2f-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="76a2f-182">att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera.</span><span class="sxs-lookup"><span data-stu-id="76a2f-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="76a2f-183">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="76a2f-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="76a2f-184">Skapa två nya namnserverposter eller ändra de befintliga namnserverposterna så att de stämmer överens med följande värden:</span><span class="sxs-lookup"><span data-stu-id="76a2f-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="76a2f-185">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="76a2f-185">First nameserver</span></span>  <br/> |<span data-ttu-id="76a2f-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="76a2f-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="76a2f-187">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="76a2f-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="76a2f-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="76a2f-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="76a2f-189">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="76a2f-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="76a2f-190">Om det finns andra namnservrar listade kan du antingen ta bort dem eller ändra dem till **ns3.dns.partner.microsoftonline.cn** och **ns4.dns.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="76a2f-191">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="76a2f-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="76a2f-192">Om du ändrar domänens NS-poster så att de pekar på Office 365 som drivs av 21Vianet-namnservrarna påverkas alla tjänster som är kopplade till domänen.</span><span class="sxs-lookup"><span data-stu-id="76a2f-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="76a2f-193">Om du hoppade över något steg i guiden, t.ex.</span><span class="sxs-lookup"><span data-stu-id="76a2f-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="76a2f-194">att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera.</span><span class="sxs-lookup"><span data-stu-id="76a2f-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="76a2f-195">Här följer exempel på några åtgärder som krävs för e-post och webbplatser:</span><span class="sxs-lookup"><span data-stu-id="76a2f-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="76a2f-196">Flytta alla e-postadresser som använder din domän Microsoft 365 du ändrar NS-posterna.</span><span class="sxs-lookup"><span data-stu-id="76a2f-196">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="76a2f-197">Vill du lägga till en domän som för tillfället används med en webbadress som www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="76a2f-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="76a2f-198">När du lägger till domänen kan du vidta åtgärder nedan för att se till att webbplatsen ligger kvar på samma plats så att personer fortfarande kan komma till webbplatsen när du har ändrat domänens NS-poster så att de pekar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76a2f-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="76a2f-199">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="76a2f-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="76a2f-200">Välj en domän på sidan **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-200">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="76a2f-201">På sidan med domäninformation väljer du **fliken DNS-poster.**</span><span class="sxs-lookup"><span data-stu-id="76a2f-201">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="76a2f-202">Välj **Add record**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-202">Select **Add record**.</span></span>

5. <span data-ttu-id="76a2f-203">Välj A **(Address)** i listrutan Type i fönstret **Add** **a custom DNS record.**</span><span class="sxs-lookup"><span data-stu-id="76a2f-203">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="76a2f-204">I rutan **Host name eller Alias** skriver du **@** .</span><span class="sxs-lookup"><span data-stu-id="76a2f-204">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="76a2f-205">I rutan **IP-adress** skriver du den statiska IP-adressen för den webbplats där den för närvarande finns.</span><span class="sxs-lookup"><span data-stu-id="76a2f-205">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="76a2f-206">Till exempel 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="76a2f-206">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="76a2f-207">Det måste vara en _statisk_ IP-adress för webbplatsen, inte en _dynamisk_ IP-adress.</span><span class="sxs-lookup"><span data-stu-id="76a2f-207">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="76a2f-208">Kontrollera med webbplatsen som är värd för din webbplats om du vill se till att du får en statisk IP-adress till den offentliga webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="76a2f-208">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="76a2f-209">Om du vill ändra TTL-inställningen för posten väljer du en ny tidslängd i **listrutan TTL.**</span><span class="sxs-lookup"><span data-stu-id="76a2f-209">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="76a2f-210">Fortsätt annars till steg 9.</span><span class="sxs-lookup"><span data-stu-id="76a2f-210">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="76a2f-211">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-211">Select **Save**.</span></span> 
    
<span data-ttu-id="76a2f-212">Du kan dessutom skapa en CNAME-post för att kunderna lättare ska kunna hitta till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="76a2f-212">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="76a2f-213">Välj **Add record**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-213">Select **Add record**.</span></span>

3.  <span data-ttu-id="76a2f-214">Välj **CNAME (Alias)** i listrutan Type i fönstret **Add** **a custom DNS record.**</span><span class="sxs-lookup"><span data-stu-id="76a2f-214">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="76a2f-215">I rutan **Host name eller Alias** skriver du **www**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-215">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="76a2f-216">Skriv det **fullständigt kvalificerade** domännamnet (FQDN) för din webbplats i rutan Pekar på adress.</span><span class="sxs-lookup"><span data-stu-id="76a2f-216">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="76a2f-217">Till exempel **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-217">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="76a2f-218">Om du vill ändra TTL-inställningen för posten väljer du en ny tidslängd i **listrutan TTL.**</span><span class="sxs-lookup"><span data-stu-id="76a2f-218">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="76a2f-219">Fortsätt annars till steg 6.</span><span class="sxs-lookup"><span data-stu-id="76a2f-219">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="76a2f-220">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="76a2f-220">Select **Save**.</span></span>

<span data-ttu-id="76a2f-221">När namnserverposterna har uppdaterats så att de pekar på Microsoft är domänkonfigurationen slutförd.</span><span class="sxs-lookup"><span data-stu-id="76a2f-221">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="76a2f-222">E-post dirigeras till Microsoft och trafiken till din webbplatsadress fortsätter att gå till din nuvarande webbplatsvärd.</span><span class="sxs-lookup"><span data-stu-id="76a2f-222">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="76a2f-223">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="76a2f-223">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="76a2f-224">Sedan är din Microsoft-e-post och andra tjänster inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="76a2f-224">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="76a2f-225">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="76a2f-225">Related content</span></span>

<span data-ttu-id="76a2f-226">[Lägg till DNS-poster för att ansluta din domän](create-dns-records-at-any-dns-hosting-provider.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="76a2f-226">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="76a2f-227">[Hitta och åtgärda problem när du har lagt till din domän eller DNS-register](find-and-fix-issues.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="76a2f-227">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="76a2f-228">[Hantera domäner](index.yml) (länksida)</span><span class="sxs-lookup"><span data-stu-id="76a2f-228">[Manage domains](index.yml) (link page)</span></span>
