---
title: Så här fungerar Safe Links i Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Funktionen Säkra länkar ger snabb verifiering av hyperlänkar i Office-dokument och i e-postmeddelanden. Läs den här artikeln om du vill veta hur ATP Safe Links fungerar.
ms.openlocfilehash: c87eef2afbb3a694d9906de0c6c43bfeb576782b
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806799"
---
# <a name="how-office-365-atp-safe-links-works"></a>Så här fungerar Safe Links i Office 365 ATP
> [!IMPORTANT] 
> För att Office 365 ATP Safe Links ska fungera korrekt måste alla Office 365-tjänster vara i samma version.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Så här fungerar ATP Safe Links med webbadresser i e-post

På en hög nivå fungerar så här [för ATP Safe Links-skydd](atp-safe-links.md) för webbadresser i e-post (finns i Office 365, inte lokalt):
  
1. Personer får e-postmeddelanden, varav vissa innehåller webbadresser.
    
2. All e-post går via Exchange Online Protection, där IP-filter (Internet Protocol) och kuvertfilter, signaturbaserat skydd mot skadlig kod, skräppost- och anti-malware-filter tillämpas. 
    
3. E-post kommer i människors inkorgar.
    
4. En användare loggar in på Office 365 och går till sin e-postkorg.
    
5. Användaren öppnar ett e-postmeddelande och klickar på en WEBBADRESS i e-postmeddelandet.
    
6. Funktionen FÖR betrodda LÄNKAR i ATP kontrollerar omedelbart webbadressen innan webbplatsen öppnas. WEBBADRESSEN identifieras som blockerad, skadlig eller säker.
        
   - Om webbadressen är till en webbplats som ingår i organisationens [anpassade blockerade webbadresser öppnas](set-up-a-custom-blocked-urls-list-wtih-atp.md)en [varningssida.](atp-safe-links-warning-pages.md) 
    
   - Om webbadressen är till en webbplats som har fastställts vara skadlig öppnas en [varningssida.](atp-safe-links-warning-pages.md) 
    
   - Om webbadressen går till en nedladdningsbar fil och organisationens [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) är konfigurerade för att skanna sådant innehåll kontrolleras den nedladdningsbara filen. 
    
   - Om webbadressen bedöms vara säker öppnas webbplatsen.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Så här fungerar ATP Safe Links med webbadresser i Office-dokument 

På en hög nivå fungerar så här för [ATP Safe Links-skydd](atp-safe-links.md) för webbadresser i Office 365 ProPlus- eller Business Premium-program (aktuella versioner av Word, Excel och PowerPoint på Windows, Mac eller i en webbläsare, Office-appar på iOS- eller Android-enheter, Visio på Windows, OneNote i en webbläsare):
  
1. Personer har installerat Office 365 ProPlus eller Business Premium på sin dator, smartphone eller surfplatta. (Eller så använder de Office i sin webbläsare.)
    
2. En användare öppnar ett Word, Excel, PowerPoint, OneNote (i webbläsaren) eller Visio (på skrivbordet) och loggar in på Office 365 Enterprise med sitt arbets- eller skolkonto. Dokumentet innehåller webbadresser.
    
3. När användaren klickar på en URL i dokumentet kontrolleras länken av tjänsten ATP Safe Links.
    
   - Om webbadressen är till en webbplats som ingår i organisationens [anpassade blockerade webbadresser](set-up-a-custom-blocked-urls-list-wtih-atp.md)visas användaren på en [varningssida](atp-safe-links-warning-pages.md).
    
   - Om webbadressen är till en webbplats som har fastställts vara skadlig, tas användaren till en [varningssida](atp-safe-links-warning-pages.md).
    
   - Om webbadressen går till en nedladdningsbar fil och [ATP Safe Links-principerna](set-up-atp-safe-links-policies.md) är konfigurerade för att skanna sådana nedladdningar kontrolleras den nedladdningsbara filen. 
    
   - Om webbadressen anses säker, användaren tas till webbplatsen.
      
   - Om URL-kontrollen misslyckas utlöses inte skyddet för säkra länkar. På skrivbordsklienterna kommer användaren att varnas innan du fortsätter till webbplatsen.
      
> [!NOTE]
> Det kan ta flera sekunder i början av varje session att kontrollera att användaren har ATP Safe Links for Office aktiverat. 
      
