---
title: Tagga dokument i en granskningsuppsättning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Tagga dokument i en granskningsuppsättning hjälper till att ta bort onödigt innehåll och identifiera relevant innehåll i Advanced eDiscovery fall.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161612"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Tagga dokument i en granskningsuppsättning i Advanced eDiscovery

Det är viktigt att ordna innehåll i en granskningsuppsättning för att slutföra olika arbetsflöden i eDiscovery-processen. Det omfattar:

- Ta bort onödigt innehåll

- Identifiera relevant innehåll
 
- Identifiera innehåll som måste granskas av en expert eller en jurist

När experter, jurister eller andra användare granskar innehåll i en granskningsuppsättning kan deras åsikter om innehållet fångas upp med hjälp av taggar. Om syftet till exempel är att undvika onödigt innehåll kan en användare tagga dokument med en tagg, till exempel "svarar inte". När innehåll har granskats och taggats kan du skapa en granskningsuppsättningssökning för att utesluta innehåll som är taggat som "icke-responsivt", vilket eliminerar det här innehållet från nästa steg i eDiscovery-arbetsflödet. Märkningspanelen kan anpassas för varje ärende så att taggarna kan stödja det avsedda granskningsarbetsflödet.

## <a name="tag-types"></a>Taggtyper

Advanced eDiscovery innehåller två typer av taggar:

- **Enkelvalstaggar** – Begränsar användare att välja en enskild tagg i en grupp. Det kan vara användbart för att säkerställa att användarna inte väljer taggar i konflikt, till exempel "responsiv" och "svarar inte". De visas som alternativknappar.

- **Flervalstaggar** – tillåt användare att markera flera taggar i en grupp. De visas som kryssrutor.

## <a name="tag-structure"></a>Taggstruktur

Förutom taggtyperna kan strukturen för hur taggar ordnas i taggpanelen användas för att göra taggningen av dokument mer intuitiv. Taggar är grupperade efter avsnitt. Med sökfunktionen för granskning kan du söka efter tagg och taggavsnitt. Det innebär att du kan skapa en granskningsuppsättningssökning för att hämta dokument som är märkta med valfri tagg i ett avsnitt.

![Tagga avsnitt i taggpanelen](../media/Tagtypes.png)

Taggar kan ordnas ytterligare genom att kapsla in dem i ett avsnitt. Om avsikten till exempel är att identifiera och tagga behörighetsinnehåll kan kapsling användas för att göra det tydligt att en användare kan tagga ett dokument som "behörig" och välja typ av behörighet genom att markera rätt kapslad tagg.

![Kapslade taggar i ett taggavsnitt](../media/Nestingtags.png)

## <a name="applying-tags"></a>Använda taggar

Det finns flera sätt att använda en tagg på innehåll.

### <a name="tagging-a-single-document"></a>Tagga ett enskilt dokument

När du visar ett dokument i en granskningsuppsättning kan du visa de taggar som en granskning kan använda genom att klicka **på Taggningspanel**.

![Klicka på Taggpanelen för att visa taggpanelen](../media/Singledoctag.png)

Då kan du använda taggar i dokumentet som visas i visningsprogrammet.

### <a name="bulk-tagging"></a>Masstaggar

Du kan masstagga genom att markera flera filer i resultatrutnätet och sedan använda taggarna i panelen Taggning som liknar taggning av enstaka dokument.  Massmarkering kan göras genom att markera taggar två gånger. Det första klicket använder taggen och det andra valet säkerställer att taggen är avmarkerad för alla valda filer.

![En skärmbild av en beskrivning av en mobiltelefon automatiskt genererad](../media/Bulktag.png)

> [!NOTE]
> Vid masstaggar visar märkningspanelen antalet filer som är märkta för varje tagg i panelen.

### <a name="tagging-in-other-review-panels"></a>Tagga i andra granskningspaneler

När du granskar dokument kan du använda de andra granskningspanelerna för att granska andra egenskaper för dokument i resultatrutnätet. Det omfattar granskning av andra relaterade dokument, e-posttrådar, nära dubbletter och hash-dubbletter. När du till exempel granskar relaterade dokument  (med hjälp av panelen Dokumentfamiljgranskning) kan du minska granskningstiden avsevärt genom att masstagga relaterade dokument. Till exempel om ett e-postmeddelande har flera bifogade filer och du vill vara säker på att hela familjen är taggad konsekvent.

Så här visar du till exempel panelen **Taggning när du** använder panelen **Dokumentfamiljgranskning:**

1. Med granskningspanelen öppen för ett markerat dokument (om listan med  relaterat innehåll visas i granskningspanelen för dokumentfamilj klickar du till exempel på **Tagga** dokument under granskningspanelen för dokumentfamilj.

   Taggpanelen visas som ett popup-fönster.

2. Välj en eller flera taggar för att använda det valda dokumentet. 

3. Om du vill tagga alla  dokument markerar du alla dokument i dokumentfamiljpanelen, klickar på Tagga dokument och väljer sedan de taggar som ska gälla för hela dokumentfamiljen.

![En skärmbild av en postbeskrivning i sociala medier som genererats automatiskt](../media/Relatedtag.png)
