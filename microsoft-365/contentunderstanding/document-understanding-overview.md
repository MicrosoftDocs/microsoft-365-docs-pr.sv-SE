---
title: Översikt av dokumenttolkning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Få en översikt av dokumenttolkning i Microsoft SharePoint Syntex.
ms.openlocfilehash: 5dd44a119dff6f5d194861c381fa28f76a6f0da7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701113"
---
# <a name="document-understanding-overview"></a>Översikt av dokumenttolkning


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Dokumenttolkning använder AI-modeller (artificiell intelligens) för att automatisera klassificeringen av filer och datautvinningen. Det fungerar bäst med ostrukturerade dokument, till exempel brev eller kontrakt. De här dokumenten måste innehålla text som kan identifieras utifrån fraser eller mönster. Med den identifierade texten anges både vilken typ av fil det är (klassificeringen) och vad du vill extrahera (dess extraherare).

> [!NOTE]
> Mer information om formulärbearbetning och scenarioexempel på dokumenttolkning finns i [Införande av SharePoint-Syntex: Kom igång-guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).

Modeller för dokumenttolkning skapas och hanteras på en typ av SharePoint-webbplats som kallas *innehållscenter*. När den används i ett SharePoint-dokumentbibliotek kopplas modellen till en innehållstyp med kolumner för att lagra den information som extraheras. Innehållstypen som du skapar lagras i galleriet för innehållstyper i SharePoint. Du kan också välja befintliga innehållstyper för att använda deras schema.

> [!NOTE]
> Skrivskyddat eller förseglade innehållstyper kan inte uppdateras, så de kan inte användas i en modell.

Lägg till *klassificerare* och *extraktorer* till modellen för dokumenttolkning för att göra följande: 

- Klassificerare används för att identifiera och klassificera dokument som har laddats upp till dokumentbiblioteket. En klassificerare kan t. ex. tränas till att identifiera alla *avtalsförnyelser* som laddas upp till biblioteket. Innehållstypen avtalsförnyelse definieras av dig när du skapar din klassificerare.

- Extraktorer hämtar information från dokumenten. Om du till exempel vill att alla avtalsförnyelser som identifieras i ditt dokumentbibliotek visar kolumnerna i vyn också *Tjänstens startdatum* och  *Klient* för varje avtalsförnyelse. 

Du kan använda exempelfiler för att träna och testa dina klassificerare och extraktorer på din modell. Exempelfiler tillhandahåller modellexemplen för vad du ska titta efter när du försöker identifiera och hämta data från filer. Till exempel kan du träna dina klassificerare för avtalsförnyelse och extraktorer med exempel på avtalsförlängningar som företaget arbetar med. Du kan också använda exempelfiler för att testa hur effektiv modellen är.

> [!NOTE]
> Om du använder optisk teckenläsning (OCR) för att skanna dokument, har Syntex en gräns på 15 sidor för modellträning.

När du har publicerat modellen använder du innehållscentret för att använda det på alla SharePoint-dokumentbibliotek som du har åtkomst till.  

## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)

[Skapa en extraktor](create-an-extractor.md)

[Skapa ett innehållscenter](create-a-content-center.md)

[Skapa en modell för formulärbearbetning](create-a-form-processing-model.md)

[Använda en modell](apply-a-model.md)   

[Skillnader mellan en modell för dokumenttolkning och en modell för formulärbearbetning](difference-between-document-understanding-and-form-processing-model.md)
  
[Översikt av formulärbearbetning](form-processing-overview.md)
