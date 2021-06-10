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
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207034"
---
# <a name="backscatter-in-eop"></a>Återspridning i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Bakåtcatter är rapporter* om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskända meddelanden) som du får för meddelanden som du inte har skickat. Skräppostavs spammare förfalskar meddelandens adress från: och de använder ofta riktiga e-postadresser för att låna ut trovärdigheten för sina meddelanden. Så om skräppostavsändare oundvikligen skickar meddelanden till mottagare som inte finns (skräppost är en stor volym) förs nämligen mål-e-postservern i princip att returnera det olevererbara meddelandet i en NDR-meddelande till den förfalskade avsändaren i från:-adressen.

I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor gör EOP alla försök att identifiera och tyst släppa meddelanden från tveksamma källor utan att generera en NDR-meddelande. Men utifrån den större volym-e-post som flödar genom tjänsten finns det alltid en möjlighet att EOP oavsiktligt skickar bakåtcatter.

Backscatterer.org har en blockeringslista (kallas även DNS-blockeringslista eller DNSBL) över e-postservrar som var ansvariga för att skicka bakåtcatter, och EOP-servrar kan visas i den här listan. Men vi försöker inte ta bort skräpposten från Backscatterer.org-blockeringslistan eftersom det inte är en lista över skräppostavseningar (via eget medgivande).

> [!TIP]
> Webbplatsen Backscatter.org () rekommenderar att tjänsten används för att kontrollera inkommande e-Valv i Valv-läge i stället för i läget Avvisa (stora e-posttjänster skickar nästan alltid en del <http://www.backscatterer.org/?target=usage> bakåtcatter).
