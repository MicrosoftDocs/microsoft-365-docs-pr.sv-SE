---
title: Exempel på meddelande när en avsändare blockeras när utgående skräppost skickas
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 'När en avsändare blockeras från tjänsten på grund av att utgående skräppost skickas får domänadministratören när du konfigurerar principen om utgående skräppost ett e-postmeddelande som liknar följande:'
ms.openlocfilehash: 537e97fe952ad9a5b2ca854c44fe6c53b642e3ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806048"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>Exempel på meddelande när en avsändare blockeras när utgående skräppost skickas

När en avsändare blockeras från tjänsten på grund av att utgående skräppost skickas får domänadministratören när du [konfigurerar principen om utgående skräppost](configure-the-outbound-spam-policy.md) ett e-postmeddelande som liknar följande: 
  
 **Avsändaradress:** spamalerts@microsoft.com 
  
 **Angående:** Meddelande om skräppost \<utanför dejd – *kontonamnet* \> blockerats från att skicka utgående e-post     
  
 **Kropp:** Detta är ett automatiskt svar från Exchange Online Protection Spam Analysis System. 
  
Du kontaktas eftersom vi har upptäckt stora mängder e-post som markerats som skräppost eller annat misstänkt beteende som kommer från din organisation. Följande e-postkonton har blockerats från att skicka e-post (de kan fortfarande ta emot e-post):
  
\<*kontonamn*  \> 
  
Det är troligt att det här e-postkontot har komprometterats. Följ dessa steg:
  
1. Lös problemet på din sida genom att:
    
  - Ändra lösenordet för kontot.
    
  - Bestämma hur kontot komprometterades.
    
  - Försiktighetsåtgärder för att säkerställa att denna sårbarhet inte kommer att utnyttjas igen.
    
  - Bekräftar att din utgående e-postkö har rensats från alla stötande meddelanden.
    
2. Kontakta Microsoft-supporten med hjälp av din vanliga kontaktkanal.
    
3. Förklara att du har en användare som är blockerad från att skicka e-post och att problemet har åtgärdats.
    
4. Agenten skapar en supportbiljett med den information som du anger och eskalerar den för att få e-postadressen eller domänen avblockerad.
    
5. När adressen har avblockerats och inte i avvaktan på några andra problem kommer du att kontaktas och aviseras till avblockeringen.
    
Tack för att du hjälper oss att kontrollera oönskad e-post.
  
Exchange Online Skydd.
  
\*\*OBS - Svara inte på detta e-postmeddelande eftersom det skickas från en oövervakad adress\*\*
  
> [!TIP]
> Du kan också kontakta supporten via de alternativ som dokumenteras på [Hjälp och support för EOP](help-and-support-for-eop.md). 
  

