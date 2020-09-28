---
title: Översikt över dokument förståelse
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Få en översikt över dokument kunskapen i Microsoft SharePoint Syntex.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294766"
---
# <a name="document-understanding-overview"></a>Översikt över dokument förståelse


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Användning av dokument med hjälp av AI-modeller (artificiell intelligens) för att automatisera klassificering av filer och extraktion av information. Den fungerar bäst med ostrukturerade dokument, till exempel brev och kontrakt. Dessa dokument måste innehålla text som kan identifieras baserat på fraser eller mönster. Den identifierade texten anger både den typ av fil den är (dess klassificering) och vad du vill extrahera (dess utdrag).

Dokument förståelse modeller skapas och hanteras i en typ av SharePoint-webbplats som kallas för *innehålls Center*. När modellen kopplas till ett SharePoint-dokumentbibliotek är den kopplad till en innehålls typ som innehåller kolumner för att lagra informationen som extraheras. Innehålls typen du skapar lagras i galleriet för SharePoint-innehålls typ. Du kan också välja att använda befintliga innehålls typer för att använda deras schema.

Gör följande om du vill lägga till *klassificerare* och *utdrag* i dina dokument: 

- Klassificerare används för att identifiera och klassificera dokument som laddas upp till dokument biblioteket. En klassificerare kan till exempel vara "utbildad" för att identifiera alla *förnyelse* dokument som laddas upp till biblioteket. Innehålls typen kontrakt förnyelse definieras av dig när du skapar en klassificerare.

- Utdrag ur dessa dokument. För alla kontrakt förnyelse dokument som identifieras i dokument biblioteket visas till exempel kolumnerna i vyn som också visar *tjänstens start datum* och  *klient* för varje kontrakts förnyelse dokument. 

Du kan använda exempelfiler för att träna och testa dina klassificerare och utdrag i din modell. Exempelfilerna innehåller exempel på vad du kan leta efter när du försöker identifiera och extrahera data från filer. Du kan till exempel utbilda dina klassificeringar och utdrag med exempel på förnyelse dokument som företaget samarbetar med. Du kan också använda exempelfiler för att testa effektiviteten hos modellen.

När du har publicerat modellen kan du använda innehålls centret för att tillämpa den på alla SharePoint-dokumentbibliotek som du har åtkomst till.  


## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)</br>
[Skapa en Extractor](create-an-extractor.md)</br>
[Skapa ett innehålls Center](create-a-content-center.md) 
 [Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)</br>
[Använda en modell](apply-a-model.md)   
[Skillnaden mellan ett dokument och en modell för formulär bearbetning](difference-between-document-understanding-and-form-processing-model.md)  
[Översikt över formulär bearbetning](form-processing-overview.md)
