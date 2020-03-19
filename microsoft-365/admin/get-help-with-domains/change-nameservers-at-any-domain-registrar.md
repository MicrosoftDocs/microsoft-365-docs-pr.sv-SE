---
title: Ändra namnservrar för att konfigurera Office 365 med valfri domänregistrator
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Läs om hur du lägger till och konfigurerar din domän i Office 365 så att dina tjänster som e-post och Skype för företag – Online använder ditt eget domännamn.
ms.custom: okr_smb
ms.openlocfilehash: 3030fc33a6d528fd6cb4e97c27cdbb7c251e9a97
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810834"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a><span data-ttu-id="9fdb4-103">Ändra namnservrar för att konfigurera Office 365 med valfri domänregistrator</span><span class="sxs-lookup"><span data-stu-id="9fdb4-103">Change nameservers to set up Office 365 with any domain registrar</span></span>

 <span data-ttu-id="9fdb4-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9fdb4-105">Kontrollera [Ställ in din domän (värdspecifika instruktioner)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) först för att se om vi har instruktioner för din registrator.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="9fdb4-106">Följ de här anvisningarna om du vill lägga till och konfigurera din domän i Office 365 så att ditt eget domännamn används för tjänster som e-post och Skype för företag - Online.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-106">Follow these instructions to add and set up your domain in Office 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="9fdb4-107">För att göra det måste du verifiera din domän och sedan ändra domänens namnservrar till Office 365, så att rätt DNS-poster kan ställas in åt dig.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-107">To do this, you'll verify your domain, and then change your domain's nameservers to Office 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="9fdb4-108">Följ dessa steg om följande uttalanden beskriver din situation:</span><span class="sxs-lookup"><span data-stu-id="9fdb4-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="9fdb4-109">Du har en egen domän och vill konfigurera den så att den fungerar tillsammans med Office 365.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-109">You have your own domain and want to set it up to work with Office 365.</span></span>
    
- <span data-ttu-id="9fdb4-p102">Du vill att Office 365 ska hantera DNS-poster åt dig. (Du kan även välja att [hantera DNS-posterna själv](../setup/add-domain.md).)</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p102">You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="9fdb4-112">Lägga till en TXT- eller MX-post för verifiering</span><span class="sxs-lookup"><span data-stu-id="9fdb4-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="9fdb4-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9fdb4-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="9fdb4-p103">Du skapar bara en av dessa poster. TXT är den vanligaste posttypen, men den stöds inte av vissa DNS-värdar. I sådana fall skapar du en MX-post istället.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="9fdb4-p104">Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fdb4-p105">Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="9fdb4-120">Hitta området på din DNS-värdleverantörs webbplats där du kan skapa en ny post</span><span class="sxs-lookup"><span data-stu-id="9fdb4-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="9fdb4-121">Logga in på din DNS-värds webbplats.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="9fdb4-122">Välj din domän.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="9fdb4-123">Gå till den sida där du kan redigera DNS-poster för din domän.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="9fdb4-124">Skapa posten</span><span class="sxs-lookup"><span data-stu-id="9fdb4-124">Create the record</span></span>

<span data-ttu-id="9fdb4-125">Beroende på om du skapar en TXT-post eller en MX-post gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="9fdb4-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="9fdb4-126">**Om du skapar en TXT-post använder du följande värden:**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fdb4-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-127">**Record Type**</span></span> <br/> |<span data-ttu-id="9fdb4-128">**Alias** eller **Host Name**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="9fdb4-129">**Värde**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-129">**Value**</span></span> <br/> |<span data-ttu-id="9fdb4-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="9fdb4-131">TXT</span><span class="sxs-lookup"><span data-stu-id="9fdb4-131">TXT</span></span>  <br/> |<span data-ttu-id="9fdb4-132">Gör något av följande: skriv **@**, lämna fältet tomt eller skriv domännamnet.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="9fdb4-133">> [!NOTE]> Olika DNS-värdar har olika krav för det här fältet.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="9fdb4-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9fdb4-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9fdb4-p106">> [!NOTE]> Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.          [Hur hittar jag detta?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="9fdb4-138">Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="9fdb4-139">**Om du skapar en MX-post ska du använda följande värden:**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fdb4-140">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-140">**Record Type**</span></span>|<span data-ttu-id="9fdb4-141">**Alias** eller **Host Name**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="9fdb4-142">**Värde**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-142">**Value**</span></span>|<span data-ttu-id="9fdb4-143">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-143">**Priority**</span></span>|<span data-ttu-id="9fdb4-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-144">**TTL**</span></span>|
|<span data-ttu-id="9fdb4-145">MX</span><span class="sxs-lookup"><span data-stu-id="9fdb4-145">MX</span></span>|<span data-ttu-id="9fdb4-146">Skriv antingen **@** eller domännamnet.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="9fdb4-p107">MS=ms *XXXXXXXX* > [!NOTE]> Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.          [Hur hittar jag detta?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="9fdb4-150">För **Prioritet**, för att undvika konflikter med MX-posten som används för e-postflöde, använder en lägre prioritet än prioritet för befintliga MX-poster.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="9fdb4-151">Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="9fdb4-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="9fdb4-152">Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="9fdb4-153">Spara posten</span><span class="sxs-lookup"><span data-stu-id="9fdb4-153">Save the record</span></span>

<span data-ttu-id="9fdb4-154">Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9fdb4-155">När Office 365 hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="9fdb4-156">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="9fdb4-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9fdb4-157">På sidan **Domäner** väljer du den domän som du verifierar.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="9fdb4-158">På **sidan Inställningar** väljer du **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="9fdb4-159">Välj **Verifiera**på **sidan Verifiera domän.**</span><span class="sxs-lookup"><span data-stu-id="9fdb4-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9fdb4-p109">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9fdb4-163">Ändra domänens namnserverposter (NS)</span><span class="sxs-lookup"><span data-stu-id="9fdb4-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="9fdb4-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="9fdb4-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="9fdb4-p110">När du kommer till det sista steget i domäninställningsguiden i Office 365 har du en sak kvar att göra. Du slutför konfigurationen av domänen med Office 365-tjänster, t.ex. e-post, genom att ändra namnserverposterna (NS-poster) hos domänregistratorn så att de pekar på de primära och sekundära Office 365-namnservrarna. Eftersom Office 365 fungerar som DNS-värd konfigureras de DNS-poster som behövs för tjänsterna automatiskt. Du kan uppdatera namnserverposterna själv genom att följa anvisningarna från domänregistratorn. Om du inte är bekant med DNS kontaktar du domänregistratorns support.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p110">When you get to the last step of the domains setup wizard in Office 365, you have one task remaining. To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary nameservers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you. You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="9fdb4-170">Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:</span><span class="sxs-lookup"><span data-stu-id="9fdb4-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="9fdb4-171">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9fdb4-172">Skapa två nya namnserverposter eller ändra de befintliga namnserverposterna så att de stämmer överens med följande värden:</span><span class="sxs-lookup"><span data-stu-id="9fdb4-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="9fdb4-173">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="9fdb4-173">First nameserver</span></span>  <br/> |<span data-ttu-id="9fdb4-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9fdb4-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9fdb4-175">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="9fdb4-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="9fdb4-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9fdb4-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="9fdb4-177">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="9fdb4-178">Om det finns några andra namnservrar i listan kan du antingen ta bort dem eller ändra dem till **ns3.bdm.microsoftonline.com** och **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="9fdb4-179">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="9fdb4-p112">Om du ändrar domänens NS-poster så att de pekar mot Office 365-namnservrarna påverkas alla tjänster som är kopplade till domänen. Om du hoppade över något steg i guiden, t.ex. att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p112">When you change your domain's NS records to point to the Office 365 nameservers, all the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="9fdb4-183">Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9fdb4-184">Skapa två nya namnserverposter eller ändra de befintliga namnserverposterna så att de stämmer överens med följande värden:</span><span class="sxs-lookup"><span data-stu-id="9fdb4-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="9fdb4-185">Första namnservern</span><span class="sxs-lookup"><span data-stu-id="9fdb4-185">First nameserver</span></span>  <br/> |<span data-ttu-id="9fdb4-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="9fdb4-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="9fdb4-187">Andra namnservern</span><span class="sxs-lookup"><span data-stu-id="9fdb4-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="9fdb4-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="9fdb4-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="9fdb4-189">Du bör använda minst två namnserverposter.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="9fdb4-190">Om det finns några andra namnservrar i listan kan du antingen ta bort dem eller ändra dem till **ns3.dns.partner.microsoftonline.cn** och **ns4.dns.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="9fdb4-191">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="9fdb4-192">När du ändrar domänens NS-poster så att de pekar på Office 365 som drivs av 21Vianet-namnservrar påverkas alla tjänster som för närvarande är associerade med domänen.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="9fdb4-193">Om du hoppade över något steg i guiden, t.ex.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="9fdb4-194">att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="9fdb4-195">Här följer exempel på några åtgärder som krävs för e-post och webbplatser:</span><span class="sxs-lookup"><span data-stu-id="9fdb4-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="9fdb4-196">Flytta alla e-postadresser som använder din domän till Office 365 innan du ändrar NS-posterna.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-196">Move all email addresses that use your domain to Office 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="9fdb4-197">Vill du lägga till en domän som för tillfället används med en webbadress som www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="9fdb4-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="9fdb4-198">Du kan göra nedan åtgärder medan du lägger till domänen för att hålla sin webbplats värd där webbplatsen är värd nu så att andra fortfarande kan komma till webbplatsen när du har ändrat domänens NS-poster för att peka på Office 365.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Office 365.</span></span>

1. <span data-ttu-id="9fdb4-199">Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="9fdb4-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="9fdb4-200">Välj en domän på sidan Domäner.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="9fdb4-201">Under **DNS-inställningar**väljer du **Anpassade poster**och väljer sedan Ny anpassad **post**.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="9fdb4-202">Välj den typ av DNS-post som du vill lägga till och skriv informationen för den nya posten.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="9fdb4-203">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9fdb4-p116">Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.</span><span class="sxs-lookup"><span data-stu-id="9fdb4-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

