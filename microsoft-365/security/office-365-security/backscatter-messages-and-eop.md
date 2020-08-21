---
title: Återspridning i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om bakEOP och Microsoft Exchange Online Protection ()
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827791"
---
# <a name="backscatter-in-eop"></a>Återspridning i EOP

*Bakgrunds rapporter som inte* kan levereras (kallas även NDR eller studsande meddelanden) som du får för meddelanden som du inte har skickat. Skräp post Forge (förfalskningar) från: adress till sina meddelanden och använder ofta riktiga e-postadresser för att ge trovärdigheten till sina meddelanden. Så när skräp post avsändare inte kan skicka meddelanden till icke befintliga mottagare (spam är en hög volym), är mål-e-postservern i huvudsak att returnera det icke-skickade meddelandet i en NDR till den förfalskade avsändaren i mappen från: adress.

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor gör EOP till att identifiera och tyst släppa meddelanden från Dubious källor utan att generera en NDR. Men baserat på skir volym e-post som flödar via tjänsten är det alltid möjligt att EOP oavsiktligt skickar en bakgrunds bild.

Backscatterer.org bevarar en block lista (kallas även DNS-blockeringslistan eller DNSBL) av e-postservrar som är ansvariga för att skicka bakgrunds-och EOP servrar kan visas i den här listan. Men det går inte att ta bort oss själva från Backscatterer.org-blockeringslistan eftersom det inte är en lista över skräp post avsändare (efter eget godkännande).

> [!TIP]
> Backscatter.org webbplats ( <http://www.backscatterer.org/?target=usage> ) rekommenderar att den används för att kontrol lera inkommande e-post i fel säkert läge (stora e-posttjänster som nästan alltid skickar lite bakmatning).
