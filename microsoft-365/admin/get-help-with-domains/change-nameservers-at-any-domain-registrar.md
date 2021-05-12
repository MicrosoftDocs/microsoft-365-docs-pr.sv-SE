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
description: Lär dig att lägga till och konfigurera din domän i Microsoft 365 så att tjänster som e-post och Skype för företag – Online använder ditt eget domännamn.
ms.openlocfilehash: 1348beb09fcbc5c12d01dbf197b1cb1240decded
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332648"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="ae96b-103">Ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator</span><span class="sxs-lookup"><span data-stu-id="ae96b-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="ae96b-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="ae96b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ae96b-105">Följ de här anvisningarna för att lägga till och konfigurera din domän i Microsoft 365 så att tjänster som e-post och Teams använder ditt eget domännamn.</span><span class="sxs-lookup"><span data-stu-id="ae96b-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="ae96b-106">Det gör du genom att verifiera domänen och sedan ändra domänens namnservrar till Microsoft 365 så att rätt DNS-poster kan ställas in åt dig.</span><span class="sxs-lookup"><span data-stu-id="ae96b-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="ae96b-107">Följ de här anvisningarna om följande påståenden beskriver din situation:</span><span class="sxs-lookup"><span data-stu-id="ae96b-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="ae96b-108">Du har en egen domän och vill konfigurera den så att den fungerar med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae96b-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="ae96b-109">Du vill att Microsoft 365 ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="ae96b-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="ae96b-110">(Du kan även välja att [hantera DNS-posterna själv](../setup/add-domain.md).)</span><span class="sxs-lookup"><span data-stu-id="ae96b-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="ae96b-111">Lägga till en TXT- eller MX-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="ae96b-111">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="ae96b-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ae96b-112"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="ae96b-p103">Du skapar bara en av dessa poster. TXT är den vanligaste posttypen, men den stöds inte av vissa DNS-värdar. I sådana fall skapar du en MX-post istället.</span><span class="sxs-lookup"><span data-stu-id="ae96b-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="ae96b-p104">Innan du använder din domän med Microsoft 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="ae96b-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae96b-p105">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="ae96b-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="ae96b-119">Ta reda på var på din DNS-värds webbplats som du kan skapa en ny post</span><span class="sxs-lookup"><span data-stu-id="ae96b-119">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="ae96b-120">Logga in på din DNS-värds webbplats.</span><span class="sxs-lookup"><span data-stu-id="ae96b-120">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="ae96b-121">Välj din domän.</span><span class="sxs-lookup"><span data-stu-id="ae96b-121">Choose your domain.</span></span>
    
3. <span data-ttu-id="ae96b-122">Gå till den sida där du kan redigera DNS-poster för din domän.</span><span class="sxs-lookup"><span data-stu-id="ae96b-122">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="ae96b-123">Skapa posten</span><span class="sxs-lookup"><span data-stu-id="ae96b-123">Create the record</span></span>

<span data-ttu-id="ae96b-124">Beroende på om du skapar en TXT-post eller en MX-post gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="ae96b-124">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="ae96b-125">**Om du skapar en TXT-post använder du följande värden:**</span><span class="sxs-lookup"><span data-stu-id="ae96b-125">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ae96b-126">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="ae96b-126">**Record Type**</span></span> <br/> |<span data-ttu-id="ae96b-127">**Alias** eller **Host Name**</span><span class="sxs-lookup"><span data-stu-id="ae96b-127">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="ae96b-128">**Värde**</span><span class="sxs-lookup"><span data-stu-id="ae96b-128">**Value**</span></span> <br/> |<span data-ttu-id="ae96b-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ae96b-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="ae96b-130">TXT</span><span class="sxs-lookup"><span data-stu-id="ae96b-130">TXT</span></span>  <br/> |<span data-ttu-id="ae96b-131">Gör något av följande: skriv **@**, lämna fältet tomt eller skriv domännamnet.</span><span class="sxs-lookup"><span data-stu-id="ae96b-131">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="ae96b-132">> [!NOTE]> Olika DNS-värdar har olika krav för det här fältet.</span><span class="sxs-lookup"><span data-stu-id="ae96b-132">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="ae96b-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ae96b-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ae96b-134">> [!NOTE]> Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="ae96b-134">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="ae96b-135">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae96b-135">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="ae96b-136">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="ae96b-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ae96b-137">Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.</span><span class="sxs-lookup"><span data-stu-id="ae96b-137">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="ae96b-138">**Om du skapar en MX-post ska du använda följande värden:**</span><span class="sxs-lookup"><span data-stu-id="ae96b-138">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ae96b-139">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="ae96b-139">**Record Type**</span></span>|<span data-ttu-id="ae96b-140">**Alias** eller **Host Name**</span><span class="sxs-lookup"><span data-stu-id="ae96b-140">**Alias** or **Host Name**</span></span>|<span data-ttu-id="ae96b-141">**Värde**</span><span class="sxs-lookup"><span data-stu-id="ae96b-141">**Value**</span></span>|<span data-ttu-id="ae96b-142">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="ae96b-142">**Priority**</span></span>|<span data-ttu-id="ae96b-143">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ae96b-143">**TTL**</span></span>|
|<span data-ttu-id="ae96b-144">MX</span><span class="sxs-lookup"><span data-stu-id="ae96b-144">MX</span></span>|<span data-ttu-id="ae96b-145">Skriv antingen **@** eller domännamnet.</span><span class="sxs-lookup"><span data-stu-id="ae96b-145">Type either **@** or your domain name.</span></span> |<span data-ttu-id="ae96b-146">MS=ms *XXXXXXXX* > [!NOTE]> Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="ae96b-146">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="ae96b-147">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae96b-147">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="ae96b-148">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="ae96b-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ae96b-149">Under **Prioritet** anger du en lägre prioritet än den som eventuella befintliga MX-poster har, för att undvika konflikter med den MX-post som används för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="ae96b-149">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="ae96b-150">Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="ae96b-150">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="ae96b-151">Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.</span><span class="sxs-lookup"><span data-stu-id="ae96b-151">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="ae96b-152">Spara posten</span><span class="sxs-lookup"><span data-stu-id="ae96b-152">Save the record</span></span>

<span data-ttu-id="ae96b-153">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="ae96b-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="ae96b-154">När Microsoft 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="ae96b-154">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="ae96b-155">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="ae96b-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ae96b-156">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="ae96b-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="ae96b-157">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-157">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="ae96b-158">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ae96b-p109">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ae96b-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="ae96b-162">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="ae96b-162">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="ae96b-163"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="ae96b-163"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="ae96b-164">När du kommer till det sista steget i domäninstallationsguiden i Microsoft 365 har du en uppgift kvar.</span><span class="sxs-lookup"><span data-stu-id="ae96b-164">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="ae96b-165">Om du vill konfigurera domänen med Microsoft 365-tjänster, till exempel e-post, ändrar du domänens namnserverposter (eller NS-poster) hos domänregistratorn så att de pekar på de primära och sekundära Microsoft 365-namnservrarna.</span><span class="sxs-lookup"><span data-stu-id="ae96b-165">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="ae96b-166">Eftersom Microsoft 365 fungerar som DNS-värd konfigureras sedan de nödvändiga DNS-posterna för dina tjänster automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ae96b-166">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="ae96b-167">Du kan uppdatera namnserverposterna själv genom att följa de steg som domänregistratorn tillhandahåller i hjälpavsnitten på sin webbplats (om det finns några).</span><span class="sxs-lookup"><span data-stu-id="ae96b-167">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="ae96b-168">Om du inte är bekant med DNS kontaktar du supporten hos domänregistratorn.</span><span class="sxs-lookup"><span data-stu-id="ae96b-168">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="ae96b-169">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="ae96b-169">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="ae96b-170">Leta reda på var på domänregistratorns webbplats som du kan ändra namnservrar för din domän eller ett område där du kan använda anpassade namnservrar.</span><span class="sxs-lookup"><span data-stu-id="ae96b-170">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="ae96b-171">Skapa namnserverposter eller redigera de befintliga namnserverposterna så att de matchar följande värden:</span><span class="sxs-lookup"><span data-stu-id="ae96b-171">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="ae96b-172">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="ae96b-172">First nameserver</span></span>  <br/> |<span data-ttu-id="ae96b-173">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ae96b-173">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ae96b-174">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="ae96b-174">Second nameserver</span></span>  <br/> |<span data-ttu-id="ae96b-175">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ae96b-175">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ae96b-176">Tredje namnserver</span><span class="sxs-lookup"><span data-stu-id="ae96b-176">Third nameserver</span></span>  <br/> |<span data-ttu-id="ae96b-177">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ae96b-177">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ae96b-178">Fjärde namnserver</span><span class="sxs-lookup"><span data-stu-id="ae96b-178">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="ae96b-179">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ae96b-179">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="ae96b-180">Det är bäst att lägga till alla fyra posterna, men om din registrator bara har stöd för två lägger du **ns1.bdm.microsoftonline.com** och **ns2.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-180">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="ae96b-181">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="ae96b-181">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="ae96b-182">När du ändrar domänens NS-poster så att de pekar på Microsoft 365-namnservrarna påverkas alla tjänster som är kopplade till domänen.</span><span class="sxs-lookup"><span data-stu-id="ae96b-182">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="ae96b-183">Om du hoppade över något steg i guiden, t.ex.</span><span class="sxs-lookup"><span data-stu-id="ae96b-183">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="ae96b-184">att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera.</span><span class="sxs-lookup"><span data-stu-id="ae96b-184">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="ae96b-185">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="ae96b-185">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="ae96b-186">Skapa två nya namnserverposter eller ändra de befintliga namnserverposterna så att de stämmer överens med följande värden:</span><span class="sxs-lookup"><span data-stu-id="ae96b-186">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="ae96b-187">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="ae96b-187">First nameserver</span></span>  <br/> |<span data-ttu-id="ae96b-188">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="ae96b-188">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="ae96b-189">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="ae96b-189">Second nameserver</span></span>  <br/> |<span data-ttu-id="ae96b-190">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="ae96b-190">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="ae96b-191">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="ae96b-191">You should use at least two nameserver records.</span></span> <span data-ttu-id="ae96b-192">Om det finns andra namnservrar listade kan du antingen ta bort dem eller ändra dem till **ns3.dns.partner.microsoftonline.cn** och **ns4.dns.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-192">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="ae96b-193">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="ae96b-193">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="ae96b-194">Om du ändrar domänens NS-poster så att de pekar på Office 365 som drivs av 21Vianet-namnservrarna påverkas alla tjänster som är kopplade till domänen.</span><span class="sxs-lookup"><span data-stu-id="ae96b-194">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="ae96b-195">Om du hoppade över något steg i guiden, t.ex.</span><span class="sxs-lookup"><span data-stu-id="ae96b-195">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="ae96b-196">att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera.</span><span class="sxs-lookup"><span data-stu-id="ae96b-196">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="ae96b-197">Här följer exempel på några åtgärder som krävs för e-post och webbplatser:</span><span class="sxs-lookup"><span data-stu-id="ae96b-197">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="ae96b-198">Flytta alla e-postadresser som använder din domän till Microsoft 365 innan du ändrar NS-posterna.</span><span class="sxs-lookup"><span data-stu-id="ae96b-198">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="ae96b-199">Vill du lägga till en domän som för tillfället används med en webbadress som www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="ae96b-199">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="ae96b-200">När du lägger till domänen kan du vidta åtgärder nedan för att se till att webbplatsen ligger kvar på samma plats så att personer fortfarande kan komma till webbplatsen när du har ändrat domänens NS-poster så att de pekar mot Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae96b-200">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="ae96b-201">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="ae96b-201">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="ae96b-202">Välj en domän på sidan **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-202">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="ae96b-203">På sidan med domäninformation väljer du **fliken DNS-poster.**</span><span class="sxs-lookup"><span data-stu-id="ae96b-203">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="ae96b-204">Välj **Add record**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-204">Select **Add record**.</span></span>

5. <span data-ttu-id="ae96b-205">Välj A **(Address)** i listrutan Type i fönstret **Add** **a custom DNS record.**</span><span class="sxs-lookup"><span data-stu-id="ae96b-205">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="ae96b-206">I rutan **Host name eller Alias** skriver du **@** .</span><span class="sxs-lookup"><span data-stu-id="ae96b-206">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="ae96b-207">I rutan **IP-adress** skriver du den statiska IP-adressen för den webbplats där den för närvarande finns.</span><span class="sxs-lookup"><span data-stu-id="ae96b-207">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="ae96b-208">Till exempel 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="ae96b-208">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="ae96b-209">Det måste vara en _statisk_ IP-adress för webbplatsen, inte en _dynamisk_ IP-adress.</span><span class="sxs-lookup"><span data-stu-id="ae96b-209">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="ae96b-210">Kontrollera med webbplatsen som är värd för din webbplats om du vill se till att du får en statisk IP-adress till den offentliga webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ae96b-210">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="ae96b-211">Om du vill ändra TTL-inställningen för posten väljer du en ny tidslängd i **listrutan TTL.**</span><span class="sxs-lookup"><span data-stu-id="ae96b-211">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="ae96b-212">Fortsätt annars till steg 9.</span><span class="sxs-lookup"><span data-stu-id="ae96b-212">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="ae96b-213">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-213">Select **Save**.</span></span> 
    
<span data-ttu-id="ae96b-214">Du kan dessutom skapa en CNAME-post för att kunderna lättare ska kunna hitta till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ae96b-214">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="ae96b-215">Välj **Add record**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-215">Select **Add record**.</span></span>

3.  <span data-ttu-id="ae96b-216">Välj **CNAME (Alias)** i listrutan Type i fönstret **Add** **a custom DNS record.**</span><span class="sxs-lookup"><span data-stu-id="ae96b-216">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="ae96b-217">I rutan **Host name eller Alias** skriver du **www**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-217">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="ae96b-218">Skriv det **fullständigt kvalificerade** domännamnet (FQDN) för din webbplats i rutan Pekar på adress.</span><span class="sxs-lookup"><span data-stu-id="ae96b-218">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="ae96b-219">Till exempel **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-219">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="ae96b-220">Om du vill ändra TTL-inställningen för posten väljer du en ny tidslängd i **listrutan TTL.**</span><span class="sxs-lookup"><span data-stu-id="ae96b-220">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="ae96b-221">Fortsätt annars till steg 6.</span><span class="sxs-lookup"><span data-stu-id="ae96b-221">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="ae96b-222">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ae96b-222">Select **Save**.</span></span>

<span data-ttu-id="ae96b-223">När namnserverposterna har uppdaterats så att de pekar på Microsoft är domänkonfigurationen slutförd.</span><span class="sxs-lookup"><span data-stu-id="ae96b-223">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="ae96b-224">E-post dirigeras till Microsoft och trafiken till din webbplatsadress fortsätter att gå till din nuvarande webbplatsvärd.</span><span class="sxs-lookup"><span data-stu-id="ae96b-224">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="ae96b-225">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="ae96b-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="ae96b-226">Sedan är din Microsoft-e-post och andra tjänster inställda på att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="ae96b-226">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
