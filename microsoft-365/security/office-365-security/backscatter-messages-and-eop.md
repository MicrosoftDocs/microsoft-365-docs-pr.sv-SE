---
title: Backscatter i EOP
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
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om Backscatter och Microsoft Exchange Online Protection (EOP)
ms.openlocfilehash: e30fa27ac359ad28e042b2d4bd446d34a2e4f1e9
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209637"
---
# <a name="backscatter-in-eop"></a>Backscatter i EOP

*Backscatter* är rapporter som inte är leveransrapporter (kallas även NDRs eller avstudsmeddelanden) som du får för meddelanden som du inte har skickat. Spammare smida (parodi) Från: adressen till sina meddelanden, och de använder ofta riktiga e-postadresser för att ge trovärdighet åt sina meddelanden. Så, när spammare oundvikligen skicka meddelanden till icke-existerande mottagare (spam är en hög volym operation), destinationen e-postservern är i huvudsak luras att returnera det olevererbara meddelandet i en NDR till förfalskade avsändaren i Från: adress.

I Microsoft 365-organisationer med postlådor i Exchange Online- eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor gör EOP allt för att identifiera och tyst släppa meddelanden från tvivelaktiga källor utan att generera en NDR. Men, baserat på den stora volymen e-post som flyter genom tjänsten, det finns alltid möjligheten att EOP oavsiktligt kommer att skicka tillbakascatter.

Backscatterer.org upprätthåller en blockeringslista (kallas även DNS-blocklista eller DNSBL) för e-postservrar som var ansvariga för att skicka tillbakascatter, och EOP-servrar kan visas i den här listan. Men vi försöker inte ta bort oss själva från Backscatterer.org blocklistan eftersom det inte är en lista över spammare (enligt deras egen entré).

> [!TIP]
> Den Backscatter.org webbplats ( <http://www.backscatterer.org/?target=usage> ) rekommenderar att du använder sin tjänst för att kontrollera inkommande e-post i felsäkert läge istället för Avvisa-läge (stora e-posttjänster nästan alltid skicka några backscatter).
