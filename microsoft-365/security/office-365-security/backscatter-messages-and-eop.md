---
title: Backscatter och EOP
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
description: Backscatter är automatiska avvisningsmeddelanden som skickas till förfalskade e-postadresser. Den Backscatterer DNSBL identifierar servrar som skickar backscatter meddelanden (som kan innehålla många legitima e-postkällor). Eftersom det inte är en spammare lista, försöker vi inte ta bort oss från Backscatterer DNSBL.
ms.openlocfilehash: 22eeec29722cf1742e096234aad95b9f6ee407e2
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895411"
---
# <a name="backscatter-and-eop"></a>Backscatter och EOP

*Backscatter* är rapporter som inte är leveransrapporter (kallas även NDRs eller avstudsmeddelanden) som du får för meddelanden som du inte har skickat. Spammare smida (parodi) Från: adressen till sina meddelanden, och de använder ofta riktiga e-postadresser för att ge trovärdighet åt sina meddelanden. Så, när spammare oundvikligen skicka meddelanden till icke-existerande mottagare (spam är en hög volym operation), destinationen e-postservern är i huvudsak luras att returnera det olevererbara meddelandet i en NDR till förfalskade avsändaren i Från: adress.

Exchange Online Protection (EOP) gör allt för att identifiera och tyst släppa meddelanden från tvivelaktiga källor utan att generera en NDR. Men, baserat på den stora volymen e-post som flyter genom tjänsten, det finns alltid möjligheten att EOP oavsiktligt kommer att skicka tillbakascatter.

Backscatterer.org upprätthåller en blockeringslista (kallas även DNS-blocklista eller DNSBL) för e-postservrar som var ansvariga för att skicka tillbakascatter, och EOP-servrar kan visas i den här listan. Men vi försöker inte ta bort oss själva från Backscatterer.org blocklistan eftersom det inte är en lista över spammare (enligt deras egen entré).

> [!TIP]
> Den Backscatter.org webbplats (<http://www.backscatterer.org/?target=usage>) rekommenderar att du använder sin tjänst för att kontrollera inkommande e-post i felsäkert läge istället för Avvisa-läge (stora e-posttjänster nästan alltid skicka några backscatter).
