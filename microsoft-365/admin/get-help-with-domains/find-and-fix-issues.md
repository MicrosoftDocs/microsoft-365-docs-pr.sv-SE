---
title: Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Lär dig att spåra eventuella problem som du stöter på när du konfigurerar en anpassad domän genom att se till att DNS-posterna är korrekt konfigurerade.
ms.openlocfilehash: 00330dea6b3401bce02779437dc047ce324dcece
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210410"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a><span data-ttu-id="4f77e-103">Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365</span><span class="sxs-lookup"><span data-stu-id="4f77e-103">Find and fix issues after adding your domain or DNS records in Office 365</span></span>

 <span data-ttu-id="4f77e-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="4f77e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4f77e-p101">Det kan vara svårt att konfigurera din domän så att den fungerar med Office 365. DNS-systemet är omständigt att arbeta med, och DNS-konfigurationen för din domän påverkar viktiga företagsfunktioner som e-post!</span><span class="sxs-lookup"><span data-stu-id="4f77e-p101">Getting your domain set up to work with Office 365 can be challenging. The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="4f77e-107">Du kan söka efter problem med domänen genom att kontrollera dess status.</span><span class="sxs-lookup"><span data-stu-id="4f77e-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="4f77e-108">Gå till > **installationsdomäner** och visa meddelandena i kolumnen **Status.** **Setup**</span><span class="sxs-lookup"><span data-stu-id="4f77e-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="4f77e-109">Om du ser ett problem väljer du Fler åtgärder (tre punkter) och väljer sedan **Kontrollera hälsotillstånd**.</span><span class="sxs-lookup"><span data-stu-id="4f77e-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="4f77e-110">Fönstret som öppnas beskriver eventuella problem med domänen.</span><span class="sxs-lookup"><span data-stu-id="4f77e-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="4f77e-111">Vad är det som händer?</span><span class="sxs-lookup"><span data-stu-id="4f77e-111">What's going on?</span></span>

- [<span data-ttu-id="4f77e-112">Kan du inte verifiera din domän?</span><span class="sxs-lookup"><span data-stu-id="4f77e-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="4f77e-113">Fungerar inte Outlook?</span><span class="sxs-lookup"><span data-stu-id="4f77e-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="4f77e-114">Allas e-post byttes till Office 365 och du ville bara att din e-post skulle byta?</span><span class="sxs-lookup"><span data-stu-id="4f77e-114">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="4f77e-115">Kan du inte bekräfta status för ideella eller skolrelaterade konton?</span><span class="sxs-lookup"><span data-stu-id="4f77e-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="4f77e-116">Fungerar inte tjänster med din domän?</span><span class="sxs-lookup"><span data-stu-id="4f77e-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="4f77e-117">Det går inte att komma åt din webbplats?</span><span class="sxs-lookup"><span data-stu-id="4f77e-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="4f77e-118">Kan du inte verifiera domänen?</span><span class="sxs-lookup"><span data-stu-id="4f77e-118">Can't verify your domain?</span></span>
<span data-ttu-id="4f77e-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4f77e-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4f77e-120">Det finns ett antal vanliga orsaker till att domänverifieringen inte fungerar som den ska:</span><span class="sxs-lookup"><span data-stu-id="4f77e-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="4f77e-p103">**Värdet för verifieringsposten är inte helt rätt.** Kontrollera att du har kopierat och klistrat in det exakta värdet i TXT-verifieringsposten hos din DNS-värd. Ett vanligt problem är att man inte har tagit med "MS ="-delen av posten. Vi behöver den också!</span><span class="sxs-lookup"><span data-stu-id="4f77e-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="4f77e-p104">**Posten har inte sparats.** På vissa DNS-värdar måste du vidta extra åtgärd för att spara zonfilen (där DNS-posten lagras) så att den uppdateras på Internet. Kontrollera att du har sparat ändringarna så att Office 365 kan se och verifiera posten.</span><span class="sxs-lookup"><span data-stu-id="4f77e-p104">**The record hasn't been saved.** At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet. Make sure you've saved your changes so Office 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="4f77e-128">**Posten har inte uppdaterats på Internet.**</span><span class="sxs-lookup"><span data-stu-id="4f77e-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="4f77e-129">Vanligtvis kan vi se den nya posten efter bara några minuter, men ibland kan det ta upp till några timmar.</span><span class="sxs-lookup"><span data-stu-id="4f77e-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="4f77e-130">Fungerar inte Outlook?</span><span class="sxs-lookup"><span data-stu-id="4f77e-130">Outlook isn't working?</span></span>
<span data-ttu-id="4f77e-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="4f77e-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="4f77e-132">Om du har konfigurerat MX-posten och andra DNS-poster rätt för din domän men e-posten inte fungerar, kan vi hjälpa dig att [lösa problemen med Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="4f77e-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span>
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="4f77e-133">Allas e-post byttes till Office 365 och du ville bara att din e-post skulle byta?</span><span class="sxs-lookup"><span data-stu-id="4f77e-133">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="4f77e-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="4f77e-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="4f77e-135">När du lägger till din domän i Office 365 uppdateras vanligtvis domänens MX-post (av dig eller Office 365) så att den pekar på Office 365, och all e-post som skickas till den domänen börjar komma till Office 365.</span><span class="sxs-lookup"><span data-stu-id="4f77e-135">When you add your domain to Office 365, typically your domain's MX record is updated (by you or Office 365) to point to Office 365, and ALL email sent to that domain will start coming to Office 365.</span></span> <span data-ttu-id="4f77e-136">Kontrollera att du har skapat postlådor i Office 365 för alla som har e-post på din domän innan du ändrar MX-posten.</span><span class="sxs-lookup"><span data-stu-id="4f77e-136">Make sure you've created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="4f77e-137">Vad händer om du inte vill flytta e-post för alla på domänen till Office 365?</span><span class="sxs-lookup"><span data-stu-id="4f77e-137">What if you don't want to move email for everyone on your domain to Office 365?</span></span> <span data-ttu-id="4f77e-138">Då kan du i stället [vidta åtgärder för att pilottesta Office 365 med bara några få e-postadresser](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span><span class="sxs-lookup"><span data-stu-id="4f77e-138">You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="4f77e-139">Kan du inte bekräfta status för ideella eller skolrelaterade konton?</span><span class="sxs-lookup"><span data-stu-id="4f77e-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="4f77e-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="4f77e-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="4f77e-141">Det finns ett par scenarier när du bara behöver verifiera organisationens domän och inte konfigurera några tjänster.</span><span class="sxs-lookup"><span data-stu-id="4f77e-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="4f77e-142">Om du till exempel vill bevisa för Office 365 att din organisation är berättigad till en skolprenumeration.</span><span class="sxs-lookup"><span data-stu-id="4f77e-142">For example, to prove to Office 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="4f77e-143">Läs vägledningen i [Verifiera din Office 365-domän för att bevisa ägarskap, ideell eller utbildningsstatus, eller för att aktivera Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) för att se till att du har slutfört alla nödvändiga steg.</span><span class="sxs-lookup"><span data-stu-id="4f77e-143">Check out the guidance in [Verify your Office 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="4f77e-144">Det är lite annorlunda för varje situation.</span><span class="sxs-lookup"><span data-stu-id="4f77e-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="4f77e-145">Fungerar inte tjänsterna med din domän?</span><span class="sxs-lookup"><span data-stu-id="4f77e-145">Services not working with your domain?</span></span>
<span data-ttu-id="4f77e-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="4f77e-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="4f77e-147">Vi kan hjälpa dig att lösa problem med DNS-inställningarna för din domän.</span><span class="sxs-lookup"><span data-stu-id="4f77e-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="4f77e-148">Domänens felsökning i Office 365 visar eventuella felaktiga poster och vad de ska innehålla.</span><span class="sxs-lookup"><span data-stu-id="4f77e-148">The domains troubleshooter in Office 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="4f77e-p111">Har du DNS korrekt konfigurerad, men e-post fungerar ändå inte i Outlook på skrivbordet? Ta en titt på [andra scenarier för e-postflöden som du kan använda med Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) och kontrollera att allt är korrekt konfigurerat för ditt företag. Eller få mer hjälp med felsökning av e-post här: [Åtgärda problem med Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="4f77e-p111">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop? Check out the [different mail flow scenarios you can have with Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) to make sure you've got things set up correctly for your business. Or get more troubleshooting help with email here: [Fix Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="4f77e-152">Går det inte att komma åt din webbplats?</span><span class="sxs-lookup"><span data-stu-id="4f77e-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="4f77e-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="4f77e-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="4f77e-154">Om du har åtgärdat ett DNS-problem men fortfarande har problem, kan du försöka med något av följande.</span><span class="sxs-lookup"><span data-stu-id="4f77e-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="4f77e-155">Personer kan inte komma åt din webbplats på www.mydomain.com: [Spåra webbplatsproblem](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span><span class="sxs-lookup"><span data-stu-id="4f77e-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span></span>
    
- <span data-ttu-id="4f77e-156">Du kan inte uppdatera din A-post eller CNAME-post att peka mot din webbplats: [Uppdatera anpassade DNS-poster i Office 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="4f77e-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Office 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
