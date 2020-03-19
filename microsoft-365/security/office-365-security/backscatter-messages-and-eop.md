---
title: Meddelanden på grund av bakåtspridning och EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Backscatter-meddelanden är automatiska avvisningsmeddelanden som skickas till förfalskade e-postadresser. Backscatterer DNSBL identifierar servrar som skickar återspridningsmeddelanden (som kan innehålla många legitima e-postkällor). Eftersom det inte är en spammare lista, försöker vi inte ta bort oss från Backscatterer DNSBL.
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/27/2020
ms.locfileid: "42808114"
---
# <a name="backscatter-messages-and-eop"></a>Meddelanden på grund av bakåtspridning och EOP

*Backscatter-meddelanden* är rapporter som inte levereras (kallas även NDR:er eller avvisningsmeddelanden) som du får för meddelanden som du inte har skickat. Spammare smider (parodi) från: adress till sina meddelanden, och de använder ofta riktiga e-postadresser för att ge trovärdighet åt sina meddelanden. Så, när en spammare oundvikligen skicka meddelanden till icke-existerande mottagare (spam är en hög volym åtgärd), destinationen e-postserver kommer sannolikt att returnera undeliverable meddelandet i en NDR, som skickas till den förfalskade avsändaren i Från: adress.

Exchange Online Protection (EOP) gör allt för att identifiera och tyst släppa meddelanden från tvivelaktiga källor utan att generera en NDR. Men baserat på den stora volymen e-post som flyter genom tjänsten, det finns alltid en möjlighet att EOP oavsiktligt kommer att skicka backscatter meddelanden.

Backscatterer.org upprätthåller en blockeringslista (kallas även en DNS-blocklista eller DNSBL) för e-postservrar som ansvarar för att skicka meddelanden till återspridning, och EOP-servrar kan visas i den här listan. Men vi försöker inte ta bort oss från Backscatterer.org blocklistan eftersom det inte är en lista över spammare (enligt egen utsago).

> [!TIP]
> Den Backscatter.org<http://www.backscatterer.org/?target=usage>webbplats ( ) rekommenderar att du använder sin tjänst för att kontrollera inkommande e-post i felsäkert läge istället för Avvisa läge (stora e-posttjänster nästan alltid skicka några backscatter-meddelanden).
