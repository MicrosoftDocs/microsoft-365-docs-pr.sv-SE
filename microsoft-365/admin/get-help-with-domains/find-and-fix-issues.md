---
title: Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365
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
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Lär dig att spåra eventuella problem som du stöter på när du konfigurerar en anpassad domän genom att se till att DNS-posterna är korrekt konfigurerade.
ms.openlocfilehash: a93318d54b950b908319fe50a0cfedefe8586036
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43115985"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a>Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Det kan vara svårt att konfigurera din domän så att den fungerar med Office 365. DNS-systemet är omständigt att arbeta med, och DNS-konfigurationen för din domän påverkar viktiga företagsfunktioner som e-post!

> [!NOTE]
> Du kan söka efter problem med domänen genom att kontrollera dess status. Gå till > **installationsdomäner** och visa meddelandena i kolumnen **Status.** **Setup** Om du ser ett problem väljer du Fler åtgärder (tre punkter) och väljer sedan **Kontrollera hälsotillstånd**. Fönstret som öppnas beskriver eventuella problem med domänen.
  
## <a name="whats-going-on"></a>Vad är det som händer?

- [Kan du inte verifiera din domän?](#cant-verify-your-domain)
    
- [Fungerar inte Outlook?](#outlook-isnt-working)
    
- [Allas e-post byttes till Office 365 och du ville bara att din e-post skulle byta?](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [Kan du inte bekräfta status för ideella eller skolrelaterade konton?](#cant-confirm-non-profit-or-school-account-status)

- [Fungerar inte tjänster med din domän?](#services-not-working-with-your-domain)
    
- [Det går inte att komma åt din webbplats?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Kan du inte verifiera domänen?
<a name="BKMK_verify"> </a>

Det finns ett antal vanliga orsaker till att domänverifieringen inte fungerar som den ska:
  
1. **Värdet för verifieringsposten är inte helt rätt.** Kontrollera att du har kopierat och klistrat in det exakta värdet i TXT-verifieringsposten hos din DNS-värd. Ett vanligt problem är att man inte har tagit med "MS ="-delen av posten. Vi behöver den också! 
    
2. **Posten har inte sparats.** På vissa DNS-värdar måste du vidta extra åtgärd för att spara zonfilen (där DNS-posten lagras) så att den uppdateras på Internet. Kontrollera att du har sparat ändringarna så att Office 365 kan se och verifiera posten. 
    
3. **Posten har inte uppdaterats på Internet.** Vanligtvis kan vi se den nya posten efter bara några minuter, men ibland kan det ta upp till några timmar. 
    
## <a name="outlook-isnt-working"></a>Fungerar inte Outlook?
<a name="BKMK_OutlookBroken"> </a>

Om du har konfigurerat MX-posten och andra DNS-poster rätt för din domän men e-posten inte fungerar, kan vi hjälpa dig att [lösa problemen med Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a>Allas e-post byttes till Office 365 och du ville bara att din e-post skulle byta?
<a name="BKMK_EmailSwitched"> </a>

När du lägger till din domän i Office 365 uppdateras vanligtvis domänens MX-post (av dig eller Office 365) så att den pekar på Office 365, och all e-post som skickas till den domänen börjar komma till Office 365. Kontrollera att du har skapat postlådor i Office 365 för alla som har e-post på din domän innan du ändrar MX-posten.
  
Vad händer om du inte vill flytta e-post för alla på domänen till Office 365? Då kan du i stället [vidta åtgärder för att pilottesta Office 365 med bara några få e-postadresser](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Kan du inte bekräfta status för ideella eller skolrelaterade konton?
<a name="BKMK_validateAcct"> </a>

Det finns ett par scenarier när du bara behöver verifiera organisationens domän och inte konfigurera några tjänster. Om du till exempel vill bevisa för Office 365 att din organisation är berättigad till en skolprenumeration.
  
Läs vägledningen i [Verifiera din Office 365-domän för att bevisa ägarskap, ideell eller utbildningsstatus, eller för att aktivera Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) för att se till att du har slutfört alla nödvändiga steg. Det är lite annorlunda för varje situation. 
  
## <a name="services-not-working-with-your-domain"></a>Fungerar inte tjänsterna med din domän?
<a name="BKMK_Test"> </a>

Vi kan hjälpa dig att lösa problem med DNS-inställningarna för din domän. Domänens felsökning i Office 365 visar eventuella felaktiga poster och vad de ska innehålla. 

> [!TIP]
> Har du DNS korrekt konfigurerad, men e-post fungerar ändå inte i Outlook på skrivbordet? Ta en titt på [andra scenarier för e-postflöden som du kan använda med Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) och kontrollera att allt är korrekt konfigurerat för ditt företag. Eller få mer hjälp med felsökning av e-post här: [Åtgärda problem med Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx). 
  
## <a name="accessing-your-website-isnt-working"></a>Går det inte att komma åt din webbplats?
<a name="BKMK_Website"> </a>

Om du har åtgärdat ett DNS-problem men fortfarande har problem, kan du försöka med något av följande.
  
- Personer kan inte komma åt din webbplats på www.mydomain.com: [Spåra webbplatsproblem](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- Du kan inte uppdatera din A-post eller CNAME-post att peka mot din webbplats: [Uppdatera anpassade DNS-poster i Office 365](../dns/add-or-edit-custom-dns-records.md)
    
