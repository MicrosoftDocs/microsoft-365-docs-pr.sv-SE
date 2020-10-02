---
title: Översikt av dokumenttolkning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Få en översikt av dokumenttolkning i Microsoft SharePoint Syntex.
ms.openlocfilehash: 3f2c463d3713048ffff7c20f2fcf6220d55d6a32
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321779"
---
# <a name="document-understanding-overview"></a>Översikt av dokumenttolkning


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Dokumenttolkning använder AI-modeller (artificiell intelligens) för att automatisera klassificeringen av filer och datautvinningen. Det fungerar bäst med ostrukturerade dokument, till exempel brev eller kontrakt. De här dokumenten måste innehålla text som kan identifieras utifrån fraser eller mönster. Med den identifierade texten anges både vilken typ av fil det är (klassificeringen) och vad du vill extrahera (dess extraherare).

Modeller för dokumenttolkning skapas och hanteras på en typ av SharePoint-webbplats som kallas *innehållscenter*. När den används i ett SharePoint-dokumentbibliotek kopplas modellen till en innehållstyp med kolumner för att lagra den information som extraheras. Innehållstypen som du skapar lagras i galleriet för innehållstyper i SharePoint. Du kan också välja befintliga innehållstyper för att använda deras schema.

Lägg till *klassificerare* och *extraktorer* till modellen för dokumenttolkning för att göra följande: 

- Klassificerare används för att identifiera och klassificera dokument som har laddats upp till dokumentbiblioteket. En klassificerare kan t. ex. tränas till att identifiera alla *avtalsförnyelser* som laddas upp till biblioteket. Innehållstypen avtalsförnyelse definieras av dig när du skapar din klassificerare.

- Extraktorer hämtar information från dokumenten. Om du till exempel vill att alla avtalsförnyelser som identifieras i ditt dokumentbibliotek visar kolumnerna i vyn också *Tjänstens startdatum* och  *Klient* för varje avtalsförnyelse. 

Du kan använda exempelfiler för att träna och testa dina klassificerare och extraktorer på din modell. Exempelfiler tillhandahåller modellexemplen för vad du ska titta efter när du försöker identifiera och hämta data från filer. Till exempel kan du träna dina klassificerare för avtalsförnyelse och extraktorer med exempel på avtalsförlängningar som företaget arbetar med. Du kan också använda exempelfiler för att testa hur effektiv modellen är.

När du har publicerat modellen använder du innehållscentret för att använda det på alla SharePoint-dokumentbibliotek som du har åtkomst till.  



## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)

[Skapa en extraktor](create-an-extractor.md)

[Skapa ett innehållscenter](create-a-content-center.md)

[Skapa en modell för formulärbearbetning](create-a-form-processing-model.md)

[Använda en modell](apply-a-model.md)   

[Skillnader mellan en modell för dokumenttolkning och en modell för formulärbearbetning](difference-between-document-understanding-and-form-processing-model.md)
  
[Översikt av formulärbearbetning](form-processing-overview.md)
