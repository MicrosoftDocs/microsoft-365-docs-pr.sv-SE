---
title: Översikt av dokumenttolkning
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Få en översikt av dokumenttolkning i Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683829"
---
# <a name="document-understanding-overview"></a>Översikt av dokumenttolkning


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Dokumenttolkning använder AI-modeller (artificiell intelligens) för att automatisera klassificeringen av filer och datautvinningen. Det fungerar bäst med ostrukturerade dokument, till exempel brev eller kontrakt. De här dokumenten måste innehålla text som kan identifieras utifrån fraser eller mönster. Med den identifierade texten anges både vilken typ av fil det är (klassificeringen) och vad du vill extrahera (dess extraherare).

> [!NOTE]
> Mer information om formulärbearbetning och scenarioexempel på dokumenttolkning finns i [Införande av SharePoint-Syntex: Kom igång-guide](./adoption-getstarted.md).

Modeller för dokumenttolkning skapas och hanteras på en typ av SharePoint-webbplats som kallas *innehållscenter*. När den används i ett SharePoint-dokumentbibliotek kopplas modellen till en innehållstyp med kolumner för att lagra den information som extraheras. Innehållstypen som du skapar lagras i galleriet för innehållstyper i SharePoint. Du kan också välja befintliga innehållstyper för att använda deras schema.

> [!NOTE]
> Skrivskyddat eller förseglade innehållstyper kan inte uppdateras, alltså de kan inte användas i en modell.

Lägg till *klassificerare* och *extraktorer* till modellen för dokumenttolkning för att göra följande: 

- Klassificerare används för att identifiera och klassificera dokument som har laddats upp till dokumentbiblioteket. En klassificerare kan t. ex. tränas till att identifiera alla *avtalsförnyelser* som laddas upp till biblioteket. Innehållstypen avtalsförnyelse definieras av dig när du skapar din klassificerare.

- Extraktorer hämtar information från dokumenten. Om du till exempel vill att alla avtalsförnyelser som identifieras i ditt dokumentbibliotek visar kolumnerna i vyn också *Tjänstens startdatum* och  *Klient* för varje avtalsförnyelse. 

Du kan använda exempelfiler för att träna och testa dina klassificerare och extraktorer på din modell. Exempelfiler tillhandahåller modellexemplen för vad du ska titta efter när du försöker identifiera och hämta data från filer. Till exempel kan du träna dina klassificerare för avtalsförnyelse och extraktorer med exempel på avtalsförlängningar som företaget arbetar med. Du kan också använda exempelfiler för att testa hur effektiv modellen är.

När du har publicerat modellen använder du innehållscentret för att använda det på alla SharePoint-dokumentbibliotek som du har åtkomst till.  

## <a name="file-limitations"></a>Filbegränsningar

Dokument för dokumenttolkning använder optisk teckenläsning (OCR) för att skanna PDF-filer, bilder och TIFF-filer, både när du utbildar en modell med exempelfiler och när du kör modellen mot filer i ett dokumentbibliotek.

Observera följande skillnader i fråga om textbaserade filer i Microsoft Office och skannade OCR-filer (PDF, bild eller TIFF):

- Office-filer: trunkeras vid 64 000 tecken (i utbildning och när de körs mot filer i ett dokumentbibliotek).

- OCR-skannade filer: det finns en gräns på 20 sidor.  

### <a name="requirements"></a>Krav

OCR-bearbetningen fungerar bäst med dokument som uppfyller följande krav:

- JPG-, PNG- eller PDF-format (text eller skannad). PDF-filer med inbäddad text är bättre, eftersom det inte blir några fel i extrahering och placering av tecken.

- Om PDF-filerna är lösenordslåsta måste du ta bort låset innan du skickar dem.

- Den kombinerade filstorleken för dokument som används för utbildning per samling får inte överstiga 50 MB och PDF-dokument bör inte ha fler än 500 sidor.

- För bilder måste måtten vara mellan 50 × 50 och 10 000 × 10 000 bildpunkter.
   > [!NOTE]
   > Bilder som är mycket breda eller har udda mått (t.ex. planritningar) kan trunkeras i OCR-processen och förlora precision.
 
- För PDF-filer måste måtten vara högst 17 x 17 tum, motsvarande pappersstorlekerna juridiska filer eller A3 och mindre.

- Om filen har skannats från pappersdokument bör skanningen vara av hög kvalitet.

- Måste använda det latinska alfabetet (engelska tecken).

> [!NOTE]
> AI Builder stöder för närvarande inte följande typer av formulärbearbetning av indata:<br>– Kryssrutor eller alternativknappar<br>– signaturer<br>– ifyllningsbara PDF-filer.

### <a name="supported-file-types"></a>Filtyper som stöds

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