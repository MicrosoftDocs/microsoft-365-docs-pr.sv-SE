---
title: Skillnaden mellan dokumentförståelse och formulärbearbetningsmodeller (förhandsversion)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Beskriver tangentskillnaden mellan dokumentöverensning och formulärbearbetningsmodeller.
ms.openlocfilehash: bceeb4b2f52ecf95aa0a23bf8970d1427088d877
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537431"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>Skillnaden mellan dokumentförståelse och formulärbearbetningsmodeller (förhandsversion)

> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

Med innehållsöverensande i Project Cortex kan du identifiera och klassificera dokument som laddas upp till SharePoint-dokumentbibliotek samt extrahera relevant information från varje fil.  Till exempel, när filer överförs till ett SharePoint-dokumentbibliotek, klassificeras alla filer som identifieras som *inköpsorder* som sådana och visas i en anpassad dokumentbiblioteksvy där de visas. Dessutom kan du hämta specifik information från varje fil (till exempel *PO-nummer* och *totalt)* och visa den i en kolumn i dokumentbiblioteksvyn. 


Med innehållsöverensing kan du skapa *modeller* för att identifiera och extrahera den information du behöver.  Det finns två typer av modeller som kan användas:

- [Modeller för dokuments förståelse](document-understanding-overview.md)
- [Formulärbearbetningsmodeller](form-processing-overview.md)

Även om båda modellerna används för i allmänhet samma ändamål, det finns viktiga skillnader som kommer att påverka vilka du kan välja att använda.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Strukturerat kontra ostrukturerat och halvstrukturerat innehåll

Använd dokumentförståelsemodeller för att identifiera och extrahera data från ostrukturerade dokument, till exempel brev eller kontrakt, där textentiteterna som du vill extrahera finns i meningar eller specifika regioner i dokumentet. Ett ostrukturerat dokument kan till exempel vara ett brev om kontraktsförlängning som kan skrivas på olika sätt. Det finns dock information som konsekvent finns i brödtexten i varje kontraktsförnyelsedokument, till exempel textsträngen "Tjänstens startdatum" följt av ett faktiskt datum.   

Använd formulärbearbetningsmodeller för att identifiera filer och extrahera data från strukturerade eller halvstrukturerade dokument, till exempel formulär eller fakturor, där du har tydliga nyckelvärdespar (till exempel *Datum: 10/1/2020*)* eller tabelldata. Som ett exempel skulle en bra kandidat för formulärbearbetning vara ett företags formulär för orderbegäran där klienter måste tillhandahålla sin information för specifika fält som finns i samma område i dokumentlayouten, till exempel *Namn,* *Telefonnummer*, *Total kostnad*, etc.  Ett skatteformulär är ett bra exempel på ett strukturerat dokument. 

## <a name="where-they-are-created"></a>Där de skapas

Dokumentförståelsemodeller skapas och hanteras på en SharePoint-webbplats för innehållscenter. Du måste ha tillgång till en content center-webbplats för att kunna skapa en dokumentöverensåningsmodell eller tillämpa en på ett SharePoint-dokumentbibliotek. 

När du skapar en modell för dokumentöversståelse skapar du en ny [SharePoint-innehållstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) som sparas i sharepoint-galleriet för innehållstyper. Du kan också använda befintliga innehållstyper för att definiera din modell om det behövs.

Formulärbearbetningsmodeller skapas i PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), men skapandet initieras direkt från ett SharePoint-dokumentbibliotek. Formulärbearbetningsmodell måste aktiveras i dokumentbiblioteket för att en användare ska kunna skapa en formulärbearbetningsmodell för den, och en administratör kan göra detta i administratörsinställningarna för innehållsförståelse. Formulärbearbetningsmodeller använder PowerAutomate-flöden för att bearbeta filer när de överförs till dokumentbiblioteket.

Formulärbearbetningsmodeller skapar också nya [SharePoint-innehållstyper](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), som också lagras i sharepoint-galleriet för innehållstyper.

## <a name="where-they-can-be-applied"></a>Om de kan tillämpas

Dokumentöverensningsmodeller kan tillämpas på olika SharePoint-dokumentbibliotek som du har åtkomst till. Du kan använda innehållscentret för att inte bara skapa en modell för dokumentöverensning, utan också för att tillämpa den på olika dokumentbibliotek. Innehållscentret ger en mer central kontroll över hur dokumentöverensåelsemodeller används och var de används, eftersom den här informationen måste samlas upp till ett innehållscenter.

Formulärbearbetningsmodeller kan för närvarande endast tillämpas på det SharePoint-dokumentbibliotek som de skapades från. Detta gör det möjligt för alla licensierade användare som har åtkomst till webbplatsen att skapa en formulärbearbetningsmodell.




 ## <a name="see-also"></a>Se även
[Utbildning: Förbättra företagets resultat med AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Skapa en klassificerare](create-a-classifier.md)</br>
[Skapa en utsutorn](create-an-extractor.md)</br>
[Använda en modell för dokuments förståelse](apply-a-model.md)</br>
[Skapa en formulärbearbetningsmodell](create-a-form-processing-model.md)</br>



  
  



