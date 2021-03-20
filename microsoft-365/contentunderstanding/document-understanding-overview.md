---
title: Översikt av dokumenttolkning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Få en översikt av dokumenttolkning i Microsoft SharePoint Syntex.
ms.openlocfilehash: e3b239260953837f70663bb6f7e2dba1676c49eb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911204"
---
# <a name="document-understanding-overview"></a>Översikt av dokumenttolkning


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Dokumenttolkning använder AI-modeller (artificiell intelligens) för att automatisera klassificeringen av filer och datautvinningen. Det fungerar bäst med ostrukturerade dokument, till exempel brev eller kontrakt. De här dokumenten måste innehålla text som kan identifieras utifrån fraser eller mönster. Med den identifierade texten anges både vilken typ av fil det är (klassificeringen) och vad du vill extrahera (dess extraherare).

> [!NOTE]
> Mer information om formulärbearbetning och scenarioexempel på dokumenttolkning finns i [Införande av SharePoint-Syntex: Kom igång-guide](./adoption-getstarted.md#document-understanding-scenario-example).

Modeller för dokumenttolkning skapas och hanteras på en typ av SharePoint-webbplats som kallas *innehållscenter*. När den används i ett SharePoint-dokumentbibliotek kopplas modellen till en innehållstyp med kolumner för att lagra den information som extraheras. Innehållstypen som du skapar lagras i galleriet för innehållstyper i SharePoint. Du kan också välja befintliga innehållstyper för att använda deras schema.

> [!NOTE]
> Skrivskyddat eller förseglade innehållstyper kan inte uppdateras, så de kan inte användas i en modell.

Lägg till *klassificerare* och *extraktorer* till modellen för dokumenttolkning för att göra följande: 

- Klassificerare används för att identifiera och klassificera dokument som har laddats upp till dokumentbiblioteket. En klassificerare kan t. ex. tränas till att identifiera alla *avtalsförnyelser* som laddas upp till biblioteket. Innehållstypen avtalsförnyelse definieras av dig när du skapar din klassificerare.

- Extraktorer hämtar information från dokumenten. Om du till exempel vill att alla avtalsförnyelser som identifieras i ditt dokumentbibliotek visar kolumnerna i vyn också *Tjänstens startdatum* och  *Klient* för varje avtalsförnyelse. 

Du kan använda exempelfiler för att träna och testa dina klassificerare och extraktorer på din modell. Exempelfiler tillhandahåller modellexemplen för vad du ska titta efter när du försöker identifiera och hämta data från filer. Till exempel kan du träna dina klassificerare för avtalsförnyelse och extraktorer med exempel på avtalsförlängningar som företaget arbetar med. Du kan också använda exempelfiler för att testa hur effektiv modellen är.

När du har publicerat modellen använder du innehållscentret för att använda det på alla SharePoint-dokumentbibliotek som du har åtkomst till.  

### <a name="file-limitations"></a>Filbegränsningar

Dokument för dokumenttolkning använder optisk teckenläsning (OCR) för att skanna PDF-filer, bilder och TIFF-filer, både när du utbildar en modell med exempelfiler och när du kör modellen mot filer i ett dokumentbibliotek.

Observera följande skillnader i fråga om textbaserade filer i Microsoft Office och skannade OCR-filer (PDF, bild eller TIFF):

- Office-filer: Vi trunkerar vid 64 000 tecken (i utbildning och när vi kör mot filer i ett dokumentbibliotek).
- OCR-skannade filer: Det finns en gräns på 20 sidor.  

#### <a name="supported-file-types"></a>Filtyper som stöds

Dokument för dokumenttolkning stöder följande filtyper:

- dokument
- docx
- eml
- heic
- heif
- htm
- html
- jpeg
- jpg
- markdown
- md
- msg
- pdf
- png
- ppt
- pptx
- rtf
- tif
- tiff
- txt
- xls
- xlsx



## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)

[Skapa en extraktor](create-an-extractor.md)

[Skapa ett innehållscenter](create-a-content-center.md)

[Skapa en modell för formulärbearbetning](create-a-form-processing-model.md)

[Använda en modell](apply-a-model.md)   

[Skillnader mellan en modell för dokumenttolkning och en modell för formulärbearbetning](difference-between-document-understanding-and-form-processing-model.md)
  
[Översikt av formulärbearbetning](form-processing-overview.md)

[Tillgänglighetsläge för SharePoint Syntex](accessibility-mode.md)