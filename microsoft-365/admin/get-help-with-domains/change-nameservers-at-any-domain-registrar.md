---
title: Ändra namnservrar för att konfigurera Microsoft 365 med valfri domän registrator
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
description: Lär dig hur du lägger till och konfigurerar din domän i Microsoft 365 så att dina tjänster som e-post och Skype för företag – Online kan använda ditt eget domän namn.
ms.openlocfilehash: a4218b03e3f23ba8bc39c5eb84b42f87a71b9a65
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658605"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="6eb36-103">Ändra namnservrar för att konfigurera Microsoft 365 med valfri domän registrator</span><span class="sxs-lookup"><span data-stu-id="6eb36-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="6eb36-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="6eb36-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6eb36-105">Markera [Konfigurera din domän (datorspecifika instruktioner)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) först för att se om vi har anvisningar för din registrator.</span><span class="sxs-lookup"><span data-stu-id="6eb36-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="6eb36-106">Följ dessa instruktioner för att lägga till och konfigurera din domän i Microsoft 365 så att dina tjänster som e-post och team kommer att använda ditt eget domän namn.</span><span class="sxs-lookup"><span data-stu-id="6eb36-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="6eb36-107">För att göra det verifierar du din domän och ändrar sedan domänens namnservrar till Microsoft 365 så att rätt DNS-poster kan konfigureras för dig.</span><span class="sxs-lookup"><span data-stu-id="6eb36-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="6eb36-108">Följ de här anvisningarna om följande påståenden beskriver din situation:</span><span class="sxs-lookup"><span data-stu-id="6eb36-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="6eb36-109">Du har en egen domän och vill konfigurera den så att den fungerar med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6eb36-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="6eb36-110">Du vill att Microsoft 365 ska hantera dina DNS-poster åt dig.</span><span class="sxs-lookup"><span data-stu-id="6eb36-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="6eb36-111">(Du kan även välja att [hantera DNS-posterna själv](../setup/add-domain.md).)</span><span class="sxs-lookup"><span data-stu-id="6eb36-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="6eb36-112">Lägga till en TXT- eller MX-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="6eb36-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="6eb36-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6eb36-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="6eb36-p103">Du skapar bara en av dessa poster. TXT är den vanligaste posttypen, men den stöds inte av vissa DNS-värdar. I sådana fall skapar du en MX-post istället.</span><span class="sxs-lookup"><span data-stu-id="6eb36-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="6eb36-p104">Innan du använder din domän med Microsoft 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="6eb36-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6eb36-p105">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="6eb36-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="6eb36-120">Hitta området på din DNS-värds webbplats där du kan skapa en ny post</span><span class="sxs-lookup"><span data-stu-id="6eb36-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="6eb36-121">Logga in på din DNS-värds webbplats.</span><span class="sxs-lookup"><span data-stu-id="6eb36-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="6eb36-122">Välj din domän.</span><span class="sxs-lookup"><span data-stu-id="6eb36-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="6eb36-123">Gå till den sida där du kan redigera DNS-poster för din domän.</span><span class="sxs-lookup"><span data-stu-id="6eb36-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="6eb36-124">Skapa posten</span><span class="sxs-lookup"><span data-stu-id="6eb36-124">Create the record</span></span>

<span data-ttu-id="6eb36-125">Beroende på om du skapar en TXT-post eller en MX-post gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="6eb36-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="6eb36-126">**Om du skapar en TXT-post använder du följande värden:**</span><span class="sxs-lookup"><span data-stu-id="6eb36-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6eb36-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="6eb36-127">**Record Type**</span></span> <br/> |<span data-ttu-id="6eb36-128">**Alias** eller **Host Name**</span><span class="sxs-lookup"><span data-stu-id="6eb36-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="6eb36-129">**Värde**</span><span class="sxs-lookup"><span data-stu-id="6eb36-129">**Value**</span></span> <br/> |<span data-ttu-id="6eb36-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6eb36-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="6eb36-131">TXT</span><span class="sxs-lookup"><span data-stu-id="6eb36-131">TXT</span></span>  <br/> |<span data-ttu-id="6eb36-132">Gör något av följande: skriv **@**, lämna fältet tomt eller skriv domännamnet.</span><span class="sxs-lookup"><span data-stu-id="6eb36-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="6eb36-133">> [!NOTE]> Olika DNS-värdar har olika krav för det här fältet.</span><span class="sxs-lookup"><span data-stu-id="6eb36-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="6eb36-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6eb36-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6eb36-135">> [!NOTE]> Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="6eb36-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="6eb36-136">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6eb36-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="6eb36-137">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="6eb36-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6eb36-138">Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.</span><span class="sxs-lookup"><span data-stu-id="6eb36-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="6eb36-139">**Om du skapar en MX-post ska du använda följande värden:**</span><span class="sxs-lookup"><span data-stu-id="6eb36-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6eb36-140">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="6eb36-140">**Record Type**</span></span>|<span data-ttu-id="6eb36-141">**Alias** eller **Host Name**</span><span class="sxs-lookup"><span data-stu-id="6eb36-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="6eb36-142">**Värde**</span><span class="sxs-lookup"><span data-stu-id="6eb36-142">**Value**</span></span>|<span data-ttu-id="6eb36-143">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="6eb36-143">**Priority**</span></span>|<span data-ttu-id="6eb36-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6eb36-144">**TTL**</span></span>|
|<span data-ttu-id="6eb36-145">MX</span><span class="sxs-lookup"><span data-stu-id="6eb36-145">MX</span></span>|<span data-ttu-id="6eb36-146">Skriv antingen **@** eller domännamnet.</span><span class="sxs-lookup"><span data-stu-id="6eb36-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="6eb36-147">MS=ms *XXXXXXXX* > [!NOTE]> Det här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="6eb36-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="6eb36-148">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6eb36-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="6eb36-149">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="6eb36-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6eb36-150">Under **Prioritet** anger du en lägre prioritet än den som eventuella befintliga MX-poster har, för att undvika konflikter med den MX-post som används för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="6eb36-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="6eb36-151">Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="6eb36-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="6eb36-152">Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.</span><span class="sxs-lookup"><span data-stu-id="6eb36-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="6eb36-153">Spara posten</span><span class="sxs-lookup"><span data-stu-id="6eb36-153">Save the record</span></span>

<span data-ttu-id="6eb36-154">Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="6eb36-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="6eb36-155">När Microsoft 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="6eb36-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="6eb36-156">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="6eb36-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6eb36-157">På sidan **Domains** väljer du den domän du verifierar.</span><span class="sxs-lookup"><span data-stu-id="6eb36-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="6eb36-158">På sidan **Setup** väljer du **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="6eb36-159">På sidan **Verify domain** väljer du **Verify**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6eb36-p109">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6eb36-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6eb36-163">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="6eb36-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="6eb36-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="6eb36-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="6eb36-165">När du kommer till det sista steget i domän installations guiden i Microsoft 365 har du en aktivitet kvar.</span><span class="sxs-lookup"><span data-stu-id="6eb36-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="6eb36-166">Om du vill konfigurera din domän med Microsoft 365-tjänster, till exempel e-post, ändrar du domänens namnserver (eller NS-poster) hos din domän registrator för att hänvisa till Microsoft 365 primära och sekundära namnservrar.</span><span class="sxs-lookup"><span data-stu-id="6eb36-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="6eb36-167">Eftersom Microsoft 365 är värd för DNS-tjänsten installeras automatiskt de DNS-poster som krävs för dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="6eb36-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="6eb36-168">Du kan uppdatera namnserverposterna själv genom att följa de steg som domänregistratorn tillhandahåller i hjälpavsnitten på sin webbplats (om det finns några).</span><span class="sxs-lookup"><span data-stu-id="6eb36-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="6eb36-169">Om du inte är bekant med DNS kontaktar du supporten hos domänregistratorn.</span><span class="sxs-lookup"><span data-stu-id="6eb36-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="6eb36-170">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="6eb36-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="6eb36-171">Hitta området på domän registratorns webbplats där du kan ändra namnservrar för din domän eller ett område där du kan använda anpassade namnservrar.</span><span class="sxs-lookup"><span data-stu-id="6eb36-171">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="6eb36-172">Skapa namnserver poster eller ändra de befintliga namnserver posterna så att de matchar följande värden:</span><span class="sxs-lookup"><span data-stu-id="6eb36-172">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="6eb36-173">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="6eb36-173">First nameserver</span></span>  <br/> |<span data-ttu-id="6eb36-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eb36-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6eb36-175">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="6eb36-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="6eb36-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eb36-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6eb36-177">Tredje namnserver</span><span class="sxs-lookup"><span data-stu-id="6eb36-177">Third nameserver</span></span>  <br/> |<span data-ttu-id="6eb36-178">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eb36-178">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6eb36-179">Fjärde namnserver</span><span class="sxs-lookup"><span data-stu-id="6eb36-179">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="6eb36-180">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6eb36-180">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="6eb36-181">Det bästa är att lägga till alla fyra poster, men om din registrator endast stöder två lägger du till **ns1.bdm.microsoftonline.com** och **ns2.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-181">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="6eb36-182">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="6eb36-182">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="6eb36-183">När du ändrar domänens NS-poster så att de pekar på Microsoft 365-namnservrar påverkas alla tjänster som är associerade till din domän.</span><span class="sxs-lookup"><span data-stu-id="6eb36-183">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6eb36-184">Om du hoppade över något steg i guiden, t.ex.</span><span class="sxs-lookup"><span data-stu-id="6eb36-184">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="6eb36-185">att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera.</span><span class="sxs-lookup"><span data-stu-id="6eb36-185">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="6eb36-186">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="6eb36-186">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="6eb36-187">Skapa två nya namnserverposter eller ändra de befintliga namnserverposterna så att de stämmer överens med följande värden:</span><span class="sxs-lookup"><span data-stu-id="6eb36-187">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="6eb36-188">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="6eb36-188">First nameserver</span></span>  <br/> |<span data-ttu-id="6eb36-189">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="6eb36-189">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="6eb36-190">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="6eb36-190">Second nameserver</span></span>  <br/> |<span data-ttu-id="6eb36-191">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="6eb36-191">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="6eb36-192">Du bör använda minst två namnserver poster.</span><span class="sxs-lookup"><span data-stu-id="6eb36-192">You should use at least two nameserver records.</span></span> <span data-ttu-id="6eb36-193">Om det finns andra namnservrar i listan kan du antingen ta bort dem eller ändra dem till **NS3.DNS.partner.microsoftonline.cn** och **NS4.DNS.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-193">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="6eb36-194">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="6eb36-194">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="6eb36-195">När du ändrar domänens NS-poster så att de pekar på Office 365 som drivs av 21Vianet namnservrar påverkas alla tjänster som är associerade till din domän.</span><span class="sxs-lookup"><span data-stu-id="6eb36-195">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6eb36-196">Om du hoppade över något steg i guiden, t.ex.</span><span class="sxs-lookup"><span data-stu-id="6eb36-196">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="6eb36-197">att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera.</span><span class="sxs-lookup"><span data-stu-id="6eb36-197">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="6eb36-198">Här följer exempel på några åtgärder som krävs för e-post och webbplatser:</span><span class="sxs-lookup"><span data-stu-id="6eb36-198">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="6eb36-199">Flytta alla e-postadresser som använder domänen till Microsoft 365 innan du ändrar NS-posterna.</span><span class="sxs-lookup"><span data-stu-id="6eb36-199">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="6eb36-200">Vill du lägga till en domän som för tillfället används med en webbadress som www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="6eb36-200">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="6eb36-201">Du kan göra nedan när du lägger till domänen för att behålla webbplatsen där webbplatsen finns, så att andra fortfarande kan komma till webbplatsen efter att du har ändrat domänens NS-poster så att de pekar på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6eb36-201">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="6eb36-202">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="6eb36-202">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="6eb36-203">På sidan **domäner** väljer du domänen och sedan **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-203">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="6eb36-204">Under **DNS-inställningar** väljer du **anpassade poster** och väljer sedan **ny anpassad post**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-204">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

4. <span data-ttu-id="6eb36-205">Välj den typ av DNS-post du vill lägga till och ange informationen för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="6eb36-205">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

5. <span data-ttu-id="6eb36-206">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6eb36-206">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6eb36-207">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet.</span><span class="sxs-lookup"><span data-stu-id="6eb36-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6eb36-208">Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="6eb36-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
