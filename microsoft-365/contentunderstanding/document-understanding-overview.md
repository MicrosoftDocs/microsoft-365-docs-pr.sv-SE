---
title: Översikt över dokumentförståelse (förhandsgranskning)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Få en översikt över dokumentöverenskommelsen i Project Cortex.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537406"
---
# <a name="document-understanding-overview-preview"></a>Översikt över dokumentförståelse (förhandsgranskning)
> [!Note] 
> Project Cortex är för närvarande i Förhandsversion. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Dokumentöverensning använder AI-modeller för att automatisera klassificeringen av filer och extrahering av information. Det fungerar bäst med ostrukturerade dokument, som brev eller kontrakt. Dokumenten bör ha text som kan identifieras baserat på fraser eller mönster. Den identifierade texten kan ange både vilken typ av fil det är (dess klassificering) och vad du vill extrahera (dess extractors).

Dokumentförståelsemodeller skapas och hanteras på en typ av SharePoint-webbplats som kallas innehållscenter. När den tillämpas på ett SharePoint-dokumentbibliotek associeras modellen med en innehållstyp som har kolumner för att lagra den information som extraheras. Den innehållstyp du skapar lagras i sharepoint-innehållstypgalleriet. Du kan också välja att använda befintliga innehållstyper för att använda deras schema.

Du kan lägga till *klassificerare* och *extraherare* i dina dokumentförståelsemodeller för att göra följande: 

- Klassificerare används för att identifiera och klassificera dokument som överförs till dokumentbiblioteket. En klassificerare kan till exempel "tränas" för att identifiera alla *kontraktsförnyelsedokument* som överförs till biblioteket. Innehållstypen kontraktsförnyelse definieras av dig när du skapar klassificeraren.

- Utdragarna hämtar information från dessa dokument. För alla dokumentförnyelsedokument som identifieras i dokumentbiblioteket visas kolumner i vyn som också visar *startdatumet* för tjänsten och *klienten* för varje kontraktsförnyelsedokument. 

Du använder exempelfiler för att träna och testa klassificerare och utsug i din modell. Exempelfiler ger dina modellexempel på vad du ska leta efter när du försöker identifiera och extrahera data från filer. Du skulle till exempel träna dina klassificeringsklassificerare och utsug av kontraktsförnyelse med exempel på kontraktsförnyelsedokument som ditt företag arbetar med. Du kan också använda exempelfiler för att testa modellens effektivitet.

När du har publicerat modellen använder du innehållscentret för att tillämpa den på alla SharePoint-dokumentbibliotek som du har åtkomst till.  


## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)</br>
[Skapa en utsutorn](create-an-extractor.md)</br>
[Skapa ett innehållscenter](create-a-content-center.md) 
 [Skapa en formulärbearbetningsmodell](create-a-form-processing-model.md)</br>
[Använda en modell](apply-a-model.md)   
[Skillnad mellan en dokumentöverensning och en formulärbearbetningsmodell](difference-between-document-understanding-and-form-processing-model.md)  
[Översikt över formulärbearbetning](form-processing-overview.md)




