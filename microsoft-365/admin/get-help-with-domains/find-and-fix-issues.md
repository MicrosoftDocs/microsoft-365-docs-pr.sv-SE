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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Lär dig att hitta de problem du kan få när du skapar en egen domän genom att kontrollera att DNS-posterna är korrekt konfigurerade.
ms.openlocfilehash: 5959cae02b87cf481fc06edd941a6da284b71736
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537553"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
Det kan vara svårt att konfigurera Microsoft 365 att konfigurera din domän så att den fungerar med andra. DNS-systemet är omständigt att arbeta med, och DNS-konfigurationen för din domän påverkar viktiga företagsfunktioner som e-post!

> [!NOTE]
> Du kan kontrollera om det finns problem med domänen genom att kontrollera dess status. Gå till **Konfigurera**  >  **domäner** och visa meddelanden i **kolumnen Status.** Om du ser ett problem väljer du de tre punkterna (fler åtgärder) och väljer sedan **Kontrollera hälsa.** Fönstret som öppnas beskriver eventuella problem som uppstår med din domän.
  
## <a name="whats-going-on"></a>Vad är det som händer?

- [Kan du inte verifiera domänen?](#cant-verify-your-domain)
    
- [Outlook fungerar inte?](#outlook-isnt-working)
    
- [Allas e-post bytte till Microsoft 365 och du ville bara att din e-post skulle växla?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Kan du inte bekräfta statusen för ett ideellt konto eller skolkonto?](#cant-confirm-non-profit-or-school-account-status)

- [Fungerar inte tjänsterna med din domän?](#services-not-working-with-your-domain)
    
- [Fungerar det inte att komma åt din webbplats?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Kan du inte verifiera domänen?
<a name="BKMK_verify"> </a>

Det finns ett antal vanliga orsaker till att domänverifieringen inte fungerar som den ska:
  
1. **Värdet för verifieringsposten är inte helt rätt.** Kontrollera att du har kopierat och klistrat in det exakta värdet i TXT-verifieringsposten hos din DNS-värd. Ett vanligt problem är att man inte har tagit med "MS ="-delen av posten. Vi behöver den också! 
    
2. **Posten har inte sparats.** På vissa DNS-värdar måste du vidta extra åtgärd för att spara zonfilen (där DNS-posten lagras) så att den uppdateras på Internet. Kontrollera att du har sparat ändringarna så att Microsoft 365 kan se och verifiera posten. 
    
3. **Posten har inte uppdaterats på Internet.** Vanligtvis kan vi se den nya posten efter bara några minuter, men ibland kan det ta upp till några timmar. 
    
## <a name="outlook-isnt-working"></a>Fungerar inte Outlook?
<a name="BKMK_OutlookBroken"> </a>

Om du har konfigurerat MX-posten och andra DNS-poster rätt för din domän men e-posten inte fungerar, kan vi hjälpa dig att [lösa problemen med Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Allas e-post bytte till Microsoft 365 och du ville bara att din e-post skulle växla?
<a name="BKMK_EmailSwitched"> </a>

När du lägger till din domän i Microsoft 365 uppdateras vanligtvis domänens MX-post (av dig eller Microsoft 365) så att den pekar på Microsoft 365, och ALL e-post som skickas till den domänen kommer Microsoft 365. Kontrollera att du har skapat postlådor i Microsoft 365 för alla som har e-post i din domän INNAN du ändrar MX-posten.
  
Vad händer om du inte vill flytta e-post för alla i din domän till Microsoft 365? Då kan du i stället vidta [åtgärder Microsoft 365 pilottestning med bara några få e-postadresser.](../setup/domains-faq.yml)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Kan du inte bekräfta statusen för ett ideellt konto eller skolkonto?
<a name="BKMK_validateAcct"> </a>

Det finns några scenarier när du bara behöver verifiera organisationens domän och inte konfigurera några tjänster. Till exempel för att bevisa Microsoft 365 att din organisation är berättigad till ett skolabonnemang.
  
Läs anvisningarna i Verifiera [din Microsoft 365-domän](../setup/domains-faq.yml) för att bevisa ägarskap, status som ideell organisation eller utbildningsstatus, eller för att aktivera Yammer för att vara säker på att du har slutfört alla steg som krävs. Det är lite olika för varje situation. 
  
## <a name="services-not-working-with-your-domain"></a>Fungerar inte tjänsterna med din domän?
<a name="BKMK_Test"> </a>

Vi kan hjälpa dig att lösa problem med DNS-inställningarna för din domän. Domänens felsökare i Microsoft 365 visar eventuella poster som behöver åtgärdas och exakt vad posterna måste anges till. 

> [!TIP]
> Har du DNS korrekt konfigurerad, men e-post fungerar ändå inte i Outlook på skrivbordet? Ta en titta på de olika scenarier för [e-postflöde som du kan](/exchange/mail-flow-best-practices/mail-flow-best-practices) ha med Microsoft 365 för att se till att allt är korrekt inställt för ditt företag. Eller få mer hjälp med felsökning av e-post här: [Åtgärda problem med Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Går det inte att komma åt din webbplats?
<a name="BKMK_Website"> </a>

Om du har åtgärdat ett DNS-problem men fortfarande har problem, kan du försöka med något av följande.
  
- Personer kan inte komma åt din webbplats på www.mydomain.com: [Spåra webbplatsproblem](../setup/add-domain.md)
    
- Du kan inte uppdatera din A-post eller CNAME-post så att den pekar på din webbplats: [Uppdatera anpassade DNS-poster i Microsoft 365](../setup/add-domain.md)

## <a name="related-content"></a>Relaterat innehåll

[Felsökning: Granska data om ändring av verifierad domän](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

