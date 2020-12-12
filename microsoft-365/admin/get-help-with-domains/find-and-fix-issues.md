---
title: Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster
f1.keywords:
- NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Lär dig hur du kan spåra eventuella problem som uppstår när du konfigurerar en anpassad domän genom att kontrol lera att DNS-posterna är korrekt konfigurerade.
ms.openlocfilehash: d2935a7fcc134f7f6d2dd06a5b4e0e0a8761ad8a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658525"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
Att konfigurera domänen så att den fungerar med Microsoft 365 kan vara utmanande. DNS-systemet är omständigt att arbeta med, och DNS-konfigurationen för din domän påverkar viktiga företagsfunktioner som e-post!

> [!NOTE]
> Du kan kontrol lera om det finns problem med din domän genom att kontrol lera dess status. Gå till **installations**  >  **domäner** och Visa meddelanden i kolumnen **status** . Om du ser ett problem väljer du fler åtgärder (tre punkter) och väljer sedan **kontrol lera hälsa**. Fönstret som öppnas beskriver eventuella problem som uppstår med din domän.
  
## <a name="whats-going-on"></a>Vad är det som händer?

- [Kan du inte verifiera din domän?](#cant-verify-your-domain)
    
- [Outlook fungerar inte?](#outlook-isnt-working)
    
- [Allas e-postmeddelanden har bytts till Microsoft 365 och du vill bara att din e-post ska bytas?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Kan du inte bekräfta statusen för inte vinst-eller skol konto?](#cant-confirm-non-profit-or-school-account-status)

- [Fungerar inte tjänster med din domän?](#services-not-working-with-your-domain)
    
- [Gick det inte att komma åt webbplatsen?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Kan du inte verifiera domänen?
<a name="BKMK_verify"> </a>

Det finns ett antal vanliga orsaker till att domänverifieringen inte fungerar som den ska:
  
1. **Värdet för verifieringsposten är inte helt rätt.** Kontrollera att du har kopierat och klistrat in det exakta värdet i TXT-verifieringsposten hos din DNS-värd. Ett vanligt problem är att man inte har tagit med "MS ="-delen av posten. Vi behöver den också! 
    
2. **Posten har inte sparats.** På vissa DNS-värdar måste du vidta extra åtgärd för att spara zonfilen (där DNS-posten lagras) så att den uppdateras på Internet. Kontrol lera att du har sparat ändringarna så att Microsoft 365 kan se och bekräfta posten. 
    
3. **Posten har inte uppdaterats på Internet.** Vanligtvis kan vi se den nya posten efter bara några minuter, men ibland kan det ta upp till några timmar. 
    
## <a name="outlook-isnt-working"></a>Fungerar inte Outlook?
<a name="BKMK_OutlookBroken"> </a>

Om du har konfigurerat MX-posten och andra DNS-poster rätt för din domän men e-posten inte fungerar, kan vi hjälpa dig att [lösa problemen med Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Allas e-postmeddelanden har bytts till Microsoft 365 och du vill bara att din e-post ska bytas?
<a name="BKMK_EmailSwitched"> </a>

När du lägger till din domän i Microsoft 365 uppdateras din domäns MX-post (av dig eller Microsoft 365) så att den pekar på Microsoft 365 och alla e-postmeddelanden som skickas till domänen kommer att komma till Microsoft 365. Kontrol lera att du har skapat post lådor i Microsoft 365 för alla som har e-post på din domän innan du ändrar MX-posten.
  
Vad gör du om du inte vill flytta e-post för alla i domänen till Microsoft 365? Du kan vidta åtgärder för att [pilot för Microsoft 365 med bara några få e-postadresser](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Kan du inte bekräfta statusen för inte vinst-eller skol konto?
<a name="BKMK_validateAcct"> </a>

Det finns ett par scenarion när du bara behöver verifiera organisationens domän och inte har konfigurerat några tjänster. Till exempel för att bevisa för Microsoft 365 som din organisation uppfyller för ett School-abonnemang.
  
Läs mer om hur du [verifierar din Microsoft 365-domän för att bevisa ägarskap, ideella eller utbildnings status eller för att aktivera Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) för att kontrol lera att du har slutfört alla nödvändiga åtgärder. Det är lite annat för varje situation. 
  
## <a name="services-not-working-with-your-domain"></a>Fungerar inte tjänsterna med din domän?
<a name="BKMK_Test"> </a>

Vi kan hjälpa dig att lösa problem med DNS-inställningarna för din domän. Domän fel sökaren i Microsoft 365 visar alla poster som behöver åtgärdas och exakt vad posterna måste anges till. 

> [!TIP]
> Har du DNS korrekt konfigurerad, men e-post fungerar ändå inte i Outlook på skrivbordet? Ta en titt på de [olika e-postflöden som du kan ha med Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) för att se till att du har rätt inställningar för ditt företag. Eller få mer hjälp med felsökning av e-post här: [Åtgärda problem med Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Går det inte att komma åt din webbplats?
<a name="BKMK_Website"> </a>

Om du har åtgärdat ett DNS-problem men fortfarande har problem, kan du försöka med något av följande.
  
- Personer kan inte komma åt din webbplats på www.mydomain.com: [Spåra webbplatsproblem](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- Du kan inte uppdatera en post eller CNAME-post så att den pekar på din webbplats: [uppdatera anpassade DNS-poster i Microsoft 365](../dns/add-or-edit-custom-dns-records.md)

## <a name="related-content"></a>Relaterat innehåll

[Felsöka: granska data för ändring av verifierade domäner](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
