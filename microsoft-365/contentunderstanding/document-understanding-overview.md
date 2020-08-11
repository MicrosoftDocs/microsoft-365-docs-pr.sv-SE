---
title: Dokument översikt (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Få en översikt över dokument kunskapen i Project cortex.
ms.openlocfilehash: bdebc8a8726a7b9a77eb9a1095f83e937cf36cb1
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612720"
---
# <a name="document-understanding-overview-preview"></a>Dokument översikt (för hands version)
> [!Note] 
> Project cortex är för närvarande för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Med dokument användning används AI-modeller för att automatisera klassificering av filer och extrahering av information. Den fungerar bäst med ostrukturerade dokument, som till exempel brev och kontrakt. Dokumenten bör innehålla text som kan identifieras baserat på fraser eller mönster. Den identifierade texten kan ange både den typ av fil den är (dess klassificering) och vad du vill extrahera (dess utdrag).

Dokument förståelse modeller skapas och hanteras i en typ av SharePoint-webbplats som kallas för innehålls Center. När den används i ett SharePoint-dokumentbibliotek är modellen kopplad till en innehålls typ som har kolumner där den extraherade informationen lagras. Innehålls typen du skapar lagras i galleriet för SharePoint-innehålls typ. Du kan också välja att använda befintliga innehålls typer för att använda deras schema.

Du kan lägga till *klassificerare* och *utdrag* i dina dokument för att göra följande: 

- Klassificerare används för att identifiera och klassificera dokument som laddas upp till dokument biblioteket. En klassificerare kan till exempel vara "utbildad" för att identifiera alla *förnyelse* dokument som laddas upp till biblioteket. Innehålls typen kontrakt förnyelse definieras av dig när du skapar en klassificerare.

- Utdrag ur dessa dokument. För alla kontrakt förnyelse dokument som identifieras i dokument biblioteket visas kolumnerna i vyn som också visar *tjänstens start datum* och *klient* för varje kontrakts förnyelse dokument. 

Du använder exempel filer för att träna och testa dina klassificerare och utdrag i din modell. Exempel på filer ger modellen ett exempel på vad du kan leta efter när du försöker identifiera och hämta data från filer. Du kan till exempel utbilda dina klassificeringar och utdrag med ett exempel på förnyelse dokument som företaget samarbetar med. Du kan också använda exempel filer för att testa effektiviteten hos modellen.

När du har publicerat modellen kan du använda innehålls centret för att tillämpa den på alla SharePoint-dokumentbibliotek som du har åtkomst till.  


## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)</br>
[Skapa en Extractor](create-an-extractor.md)</br>
[Skapa ett innehålls Center](create-a-content-center.md) 
 [Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)</br>
[Använda en modell](apply-a-model.md)   
[Skillnaden mellan ett dokument och en modell för formulär bearbetning](difference-between-document-understanding-and-form-processing-model.md)  
[Översikt över formulär bearbetning](form-processing-overview.md)




