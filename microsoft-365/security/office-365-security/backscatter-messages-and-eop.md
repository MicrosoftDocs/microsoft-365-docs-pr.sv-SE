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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om bakåtcatter och Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286975"
---
# <a name="backscatter-in-eop"></a>Återspridning i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*Bakåtcatter är* rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskända meddelanden) som du får för meddelanden som du inte har skickat. Skräppostavsmedlare förfalskar från-adressen till sina meddelanden, och de använder ofta riktiga e-postadresser för att låna ut trovärdigheten för sina meddelanden. Så om skräppostavsändare oundvikligen skickar meddelanden till mottagare som inte finns (skräppost är en stor volymåtgärd), luras mål-e-postservern i princip att returnera det olevererbara meddelandet i en NDR-meddelande till den förfalskade avsändaren i från-adressen.

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor gör EOP allt för att identifiera och tyst släppa meddelanden från tveksamma källor utan att generera en NDR. Men utifrån den större mängd e-post som flödar genom tjänsten finns det alltid en möjlighet att EOP oavsiktligt skickar bakåtcatter.

Backscatterer.org en blockeringslista (kallas även DNS-blockeringslista eller DNSBL) över e-postservrar som ansvarar för att skicka bakåtcatter, och EOP-servrar kan visas i den här listan. Men vi försöker inte ta bort dig från blockeringslistan i Backscatterer.org för att det inte är en lista över skräppostavs skräppostavsägare (enligt eget medgivande).

> [!TIP]
> Webbplatsen Backscatter.org () rekommenderar att du använder tjänsten för att kontrollera inkommande e-post i felsäkert läge i stället för i läget Avvisa (stora e-posttjänster skickar nästan alltid <http://www.backscatterer.org/?target=usage> bakåt).
