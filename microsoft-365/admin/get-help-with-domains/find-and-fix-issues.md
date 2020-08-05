---
title: Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Lär dig att spåra eventuella problem som du stöter på när du konfigurerar en anpassad domän genom att se till att DNS-posterna är korrekt konfigurerade.
ms.openlocfilehash: 0a315be243395940146479e05de2c7044a5a36ab
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560257"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Det kan vara svårt att konfigurera domänen så att den fungerar med Microsoft 365. DNS-systemet är omständigt att arbeta med, och DNS-konfigurationen för din domän påverkar viktiga företagsfunktioner som e-post!

> [!NOTE]
> Du kan söka efter problem med domänen genom att kontrollera dess status. Gå **Setup**till  >  **installationsdomäner** och visa meddelandena i kolumnen **Status.** Om ett problem visas väljer du Fler åtgärder (tre punkter) och väljer sedan **Kontrollera hälsotillstånd**. Fönstret som öppnas beskriver eventuella problem med domänen.
  
## <a name="whats-going-on"></a>Vad är det som händer?

- [Kan du inte verifiera din domän?](#cant-verify-your-domain)
    
- [Fungerar inte Outlook?](#outlook-isnt-working)
    
- [Allas e-post fick byta till Microsoft 365 och du ville bara din e-post att byta?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Kan du inte bekräfta status för ideella eller skolrelaterade konton?](#cant-confirm-non-profit-or-school-account-status)

- [Fungerar inte tjänster med din domän?](#services-not-working-with-your-domain)
    
- [Det går inte att komma åt din webbplats?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Kan du inte verifiera domänen?
<a name="BKMK_verify"> </a>

Det finns ett antal vanliga orsaker till att domänverifieringen inte fungerar som den ska:
  
1. **Värdet för verifieringsposten är inte helt rätt.** Kontrollera att du har kopierat och klistrat in det exakta värdet i TXT-verifieringsposten hos din DNS-värd. Ett vanligt problem är att man inte har tagit med "MS ="-delen av posten. Vi behöver den också! 
    
2. **Posten har inte sparats.** På vissa DNS-värdar måste du vidta extra åtgärd för att spara zonfilen (där DNS-posten lagras) så att den uppdateras på Internet. Kontrollera att du har sparat ändringarna så att Microsoft 365 kan se och verifiera posten. 
    
3. **Posten har inte uppdaterats på Internet.** Vanligtvis kan vi se den nya posten efter bara några minuter, men ibland kan det ta upp till några timmar. 
    
## <a name="outlook-isnt-working"></a>Fungerar inte Outlook?
<a name="BKMK_OutlookBroken"> </a>

Om du har konfigurerat MX-posten och andra DNS-poster rätt för din domän men e-posten inte fungerar, kan vi hjälpa dig att [lösa problemen med Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Allas e-post fick byta till Microsoft 365 och du ville bara din e-post att byta?
<a name="BKMK_EmailSwitched"> </a>

När du lägger till din domän i Microsoft 365 uppdateras vanligtvis domänens MX-post (av dig eller Microsoft 365) så att den pekar på Microsoft 365, och all e-post som skickas till den domänen börjar komma till Microsoft 365. Kontrollera att du har skapat postlådor i Microsoft 365 för alla som har e-post på din domän innan du ändrar MX-posten.
  
Vad händer om du inte vill flytta e-post för alla på domänen till Microsoft 365? Du kan vidta åtgärder för att [testa Microsoft 365 med bara några e-postadresser istället](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Kan du inte bekräfta status för ideella eller skolrelaterade konton?
<a name="BKMK_validateAcct"> </a>

Det finns ett par scenarier när du bara behöver verifiera organisationens domän och inte konfigurera några tjänster. Om du till exempel vill bevisa för Microsoft 365 att din organisation är berättigad till en skolprenumeration.
  
Läs vägledningen i [Verifiera din Microsoft 365-domän för att bevisa ägarskap, ideell eller utbildningsstatus, eller för att aktivera Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) för att se till att du har slutfört alla nödvändiga steg. Det är lite annorlunda för varje situation. 
  
## <a name="services-not-working-with-your-domain"></a>Fungerar inte tjänsterna med din domän?
<a name="BKMK_Test"> </a>

Vi kan hjälpa dig att lösa problem med DNS-inställningarna för din domän. Felsökaren för domäner i Microsoft 365 visar alla poster som behöver åtgärdas och exakt vad posterna måste ställas in på. 

> [!TIP]
> Har du DNS korrekt konfigurerad, men e-post fungerar ändå inte i Outlook på skrivbordet? Kolla in de [olika scenarier för e-postflödet du kan ha med Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) för att se till att du har konfigurerat saker på rätt sätt för ditt företag. Eller få mer hjälp med felsökning av e-post här: [Åtgärda problem med Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Går det inte att komma åt din webbplats?
<a name="BKMK_Website"> </a>

Om du har åtgärdat ett DNS-problem men fortfarande har problem, kan du försöka med något av följande.
  
- Personer kan inte komma åt din webbplats på www.mydomain.com: [Spåra webbplatsproblem](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- Du kan inte uppdatera A-posten eller CNAME-posten så att den pekar på din webbplats: [Uppdatera anpassade DNS-poster i Microsoft 365](../dns/add-or-edit-custom-dns-records.md)
    
