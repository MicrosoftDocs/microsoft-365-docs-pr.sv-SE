---
title: Använda kommunikationsredigeraren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Använd kommunikationsredigeraren för att ändra text- och kopplingsfältvariabler när du formaterar innehållet.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161774"
---
# <a name="use-the-communications-editor"></a>Använda kommunikationsredigeraren

När du definierar innehållet på portalens innehåll, aviseringar om juridiska meddelanden och relaterade påminnelser/eskalering kan du använda kommunikationsredigeraren för att formatera och dynamiskt anpassa innehållet.

## <a name="rich-text-editor"></a>RTF-redigerare

Med Kommunikationsredigeraren kan du anpassa texten med redigeringsalternativen. Användare kan till exempel ändra teckensnitt, skapa punktlistor, markera innehåll och mycket mer.

## <a name="merge-field-variables"></a>Sammanfoga fältvariabler

Du kan använda variabler för sammanfogning av e-post från Kommunikationsredigeraren för att bädda in anpassade attribut i brödtexten i en kommunikation. När de skickas till den dokumenterade uppslagsinstruktionen fylls den i med motsvarande fält. När den skickades till dokumenterianen Johan Svensson skulle till exempel kopplingsinstruktionen [Förnamn] översättas med motsvarande namn.

Du kan använda kopplingsinstruktioner för e-post **genom** att välja ikonerna för kopplingsinstruktionen högst upp i RTF-redigeraren. Platshållaren läggs till utifrån platsen för användarens markör.

### <a name="list-of-merge-field-variables"></a>Lista över kopplingsinstruktionsvariabler

| Fältnamn                  | Fältinformation |
| :------------------- | :------------------- |
| Visningsnamn  | Den som ger sig av för- och efternamn. | 
| Bekräftelselänk | En anpassad länk för att registrera varje enskild persons bekräftelse.|                 |
| Portallänk     | En anpassad länk för den uppsnadares efterlevnadsportal.|                |
| Utfärdar officer                   | E-postadressen till den angivna utfärdaren.|                   |
| Utgivningsdatum                   | Datumet då meddelandet utfärdades (UTC).              |
|||
