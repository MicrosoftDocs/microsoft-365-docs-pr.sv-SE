---
title: Så fungerar ATP – säkra länkar
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
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Med funktionen för säkra länkar kan du klicka på verifiering av hyperlänkar i Office-dokument och i e-postmeddelanden. Läs den här artikeln för att få reda på hur säkerhets länkar i ATP fungerar.
ms.openlocfilehash: 09357b20173e2609587137764737c8aba044190e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201478"
---
# <a name="how-atp-safe-links-works"></a>Så fungerar ATP – säkra länkar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> För att Office 365 ska få säkra Länkar för att fungera korrekt måste alla tjänsterna finnas i samma version.
         
## <a name="how-atp-safe-links-works"></a>Så fungerar ATP – säkra länkar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 med URL: er via e-post

På en hög nivå, så här gör du så här för att skydda dina URL [-adresser i](atp-safe-links.md) e-post (som finns i Office 365, inte lokalt):
  
1. Personer får e-postmeddelanden, varav vissa innehåller URL: er.
    
2. All e-post går genom Exchange Online Protection, där IP (Internet Protocol) och kuvert filter, signaturbaserade skydd mot skadlig program vara samt filter mot skräp post. 
    
3. E-post anländer till personers inkorgar.
    
4. En användare loggar in i Office 365 och går till deras e-postinkorg.
    
5. Användaren öppnar ett e-postmeddelande och klickar på en URL i e-postmeddelandet.
    
6. Med funktionen för Safet ATP-länkar kontrol leras URL-adressen omedelbart innan webbplatsen öppnas. URL: en identifieras som blockerad, skadlig eller säker.
        
   - Om URL-adressen är till en webbplats som ingår i organisationens [anpassade lista över blockerade URL-adresser](set-up-a-custom-blocked-urls-list-atp.md)öppnas en [varnings sida](atp-safe-links-warning-pages.md) . 
    
   - Om URL-adressen är till en webbplats som har bedömts vara skadlig visas en [varnings sida](atp-safe-links-warning-pages.md) . 
    
   - Om URL-adressen går till en nedladdnings bar fil och organisationens [principer för Safet ATP-länkar](set-up-atp-safe-links-policies.md) är konfigurerade för genomsökning av sådant innehåll är den nedladdnings bara filen markerad. 
    
   - Om webb adressen är säker öppnas webbplatsen.
    
## <a name="how-atp-safe-links-works"></a>Så fungerar ATP – säkra länkar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 med URL-adresser i Office-dokument 

På en hög nivå, så här gör du så här för att skydda dina URL [-adresser i](atp-safe-links.md) Microsoft 365-appar för Enterprise-eller Business Premium-program (aktuella versioner av Word, Excel och PowerPoint på Windows, Mac eller i en webbläsare, Office-appar på iOS-eller Android-enheter, Visio på Windows, OneNote i en webbläsare):
  
1. Personer har installerat Microsoft 365-appar för företag eller företag Premium på sin dator, smartphone eller surfplatta. (Eller så använder de Office i webbläsaren.)
    
2. En användare öppnar ett ord, Excel, PowerPoint, OneNote (i webbläsaren) eller Visio (på Skriv bordet) och loggar in på Office 365 Enterprise med sitt arbets-eller skol konto. Dokumentet innehåller URL: er.
    
3. När användaren klickar på en URL i dokumentet kontrol leras länken av tjänsten ATP Safe Links.
    
   - Om URL-adressen är till en webbplats som ingår i organisationens [anpassade lista över blockerade URL-adresser](set-up-a-custom-blocked-urls-list-atp.md), kommer användaren till en [varnings sida](atp-safe-links-warning-pages.md).
    
   - Om URL-adressen är till en webbplats som har bedömts vara skadlig, kommer användaren till en [varnings sida](atp-safe-links-warning-pages.md).
    
   - Om URL-adressen går till en nedladdnings bar fil och [principer för Safet ATP-länkar](set-up-atp-safe-links-policies.md) är konfigurerade för att söka igenom sådana nedladdningar är nedladdnings bar fil markerad. 
    
   - Om URL: en anses vara säker kommer användaren till webbplatsen.
      
   - Om webb adress kontrollen inte fungerar utlöses inte säkra länkar. Användaren får ett varnings meddelande innan de fortsätter genom till webbplatsen.
      
> [!NOTE]
> Det kan ta flera sekunder i början av varje session att kontrol lera att användaren har Safet ATP-Länkar för Office. 
      
