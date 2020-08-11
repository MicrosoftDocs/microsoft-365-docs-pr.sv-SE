---
title: Skillnad mellan dokument förståelse och modeller för formulär bearbetning (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Beskriver viktig skillnad mellan dokument-och formulär bearbetnings modeller.
ms.openlocfilehash: 7c480b91c1ddd75016b4bd35faa3d5692cacd103
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612744"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>Skillnad mellan dokument förståelse och modeller för formulär bearbetning (för hands version)

> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

Med innehålls förståelse i Project cortex kan du identifiera och klassificera dokument som laddas upp till SharePoint-dokumentbibliotek, samt att extrahera relevant information från varje fil.  När till exempel filer laddas upp till ett SharePoint-dokumentbibliotek klassificeras alla filer som identifieras som *inköps order* som sådana och visas i en anpassad vy för dokument bibliotek. Dessutom kan du hämta specifik information från varje fil (till exempel *inköps order nummer* och *totalt*) och visa den i en kolumn i vyn dokument bibliotek. 


Med innehålls förståelse kan du skapa *modeller* för att identifiera och extrahera den information du behöver.  Det finns två typer av modeller som kan användas:

- [Förstå dokument](document-understanding-overview.md)
- [Formulär bearbetnings modeller](form-processing-overview.md)

Även om båda modellerna används i samma syfte är det viktiga skillnader som påverkar vilka du kan välja att använda.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Strukturerat kontra ostrukturerat och indelat innehåll

Använd dokument förståelse modeller för att identifiera och hämta data från ostrukturerade dokument, till exempel bokstäver eller kontrakt, där de textenheter som du vill extrahera finns i meningar eller vissa områden i dokumentet. Ett ostrukturerat dokument kan till exempel vara ett förnyelse brev som kan skrivas på olika sätt. Men det finns information som är konsekvent i bröd texten i varje kontrakt förnyelse dokument, till exempel text strängen "start datum" följt av ett faktiskt datum.   

Använd formulär bearbetnings modeller för att identifiera filer och hämta data från strukturerade eller halv strukturerade dokument, till exempel formulär eller fakturor, där du har tydliga par av viktiga värden (t. ex. *datum: 10/1/2020*) * eller tabell data. Som ett exempel är en bra kandidat för formulär bearbetning att skapa ett företags order förfrågnings formulär där klienter behöver uppge sin information för specifika fält som finns i samma område i dokumentlayouten, till exempel *namn*, *telefonnummer*, *Total kostnad*etc.  Ett moms formulär är ett bra exempel på ett strukturerat dokument. 

## <a name="where-they-are-created"></a>Var de skapas

Dokument förståelse modeller skapas och hanteras på en webbplats för SharePoint-innehåll. Du måste ha till gång till en innehålls Center webbplats för att skapa en dokument modell eller för att använda en i ett SharePoint-dokumentbibliotek. 

När du skapar en dokument metod kan du skapa en ny [SharePoint-innehållstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) som sparas i galleriet för SharePoint-innehålls typer. Du kan också använda befintliga innehålls typer för att definiera modellen om det behövs.

Formulär bearbetnings modeller skapas i PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)men skapandet startas direkt från ett SharePoint-dokumentbibliotek. Skapande av formulär bearbetnings modeller måste aktive ras i dokument biblioteket för att en användare ska kunna skapa en formulär bearbetnings modell för det och en administratör kan göra detta i administratörs inställningarna för innehåll. För formulär bearbetnings modeller används PowerAutomate-flöden för att bearbeta filer när de överförs till dokument biblioteket.

Formulär bearbetnings modeller skapar också nya [SharePoint-innehålls typer](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), som också lagras i galleriet SharePoint-innehålls typer.

## <a name="where-they-can-be-applied"></a>Var de kan användas

Dokument förståelse modeller kan tillämpas på olika SharePoint-dokumentbibliotek som du har åtkomst till. Du kan använda innehålls centret för att inte bara skapa en dokument förståelse, utan även för att tillämpa den på olika dokument bibliotek. Innehålls Center ger en mer Central kontroll av hur dokument tolka modeller används och var de används, eftersom dessa uppgifter måste lyftas upp till ett innehålls Center.

Formulär bearbetnings modeller kan för närvarande endast användas i det SharePoint-dokumentbibliotek som de skapades från. Då kan alla licensierade användare som har åtkomst till webbplatsen skapa en modell för formulär bearbetning.




 ## <a name="see-also"></a>Se även
[Utbildning: förbättra företags prestanda med hjälp av AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Skapa en klassificerare](create-a-classifier.md)</br>
[Skapa en Extractor](create-an-extractor.md)</br>
[Använda en modell för dokument förståelse](apply-a-model.md)</br>
[Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)</br>



  
  



