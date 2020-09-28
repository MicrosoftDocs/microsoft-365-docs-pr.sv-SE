---
title: Skillnad mellan dokument-och formulär bearbetnings modeller
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Här beskrivs viktig skillnad mellan dokument-och formulär bearbetnings modeller
ms.openlocfilehash: 268a2fa4a0381e5822c17e5df22566c931d37f3c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294754"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Skillnad mellan dokument-och formulär bearbetnings modeller 

Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

Med innehålls förståelse i Project cortex kan du identifiera och klassificera dokument som laddas upp till SharePoint-dokumentbibliotek, samt att extrahera relevant information från varje fil.  När till exempel filer laddas upp till ett SharePoint-dokumentbibliotek klassificeras alla filer som identifieras som *inköps order* som sådana och visas sedan i en anpassad vy för dokument bibliotek. Dessutom kan du hämta specifik information från varje fil (till exempel *inköps order nummer* och *totalt*) och visa den som en kolumn i vyn dokument bibliotek. 

Med innehålls förståelse kan du skapa *modeller* för att identifiera och extrahera den information du behöver. Det här är två modell typer som du kan använda:

- [Förstå dokument](document-understanding-overview.md)
- [Formulär bearbetnings modeller](form-processing-overview.md)

Även om båda modellerna vanligt vis används för samma ändamål påverkar de viktigaste skillnaderna som visas nedan de som du kan använda.

## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Strukturerat kontra ostrukturerat och indelat innehåll

Använd dokument förståelse modeller för att identifiera och hämta data från ostrukturerade dokument, till exempel bokstäver eller kontrakt, där de textenheter som du vill extrahera finns i meningar eller vissa områden i dokumentet. Ett ostrukturerat dokument kan till exempel vara ett förnyelse brev som kan skrivas på olika sätt. Men det finns information på ett enhetligt sätt i bröd texten i varje kontrakt förnyelse dokument, till exempel text strängen "start datum", följt av ett faktiskt datum.   

Använd formulär bearbetnings modeller för att identifiera filer och hämta data från strukturerade eller halv strukturerade dokument, till exempel formulär och fakturor. Dessa dokument måste innehålla rader med tydliga par-värden (till exempel *date: 10/1/2020*) * eller tabell data. Ett exempel är att en bra kandidat för formulär bearbetning är ett företags order förfrågnings formulär som klienter behöver för att tillhandahålla information om specifika fält som finns i samma område i dokumentlayouten, till exempel *namn*, *telefonnummer*, *Total kostnad*etc.  Ett moms formulär är ett bra exempel på ett strukturerat dokument. 

## <a name="where-they-are-created"></a>Var de skapas

Dokument förståelse modeller skapas och hanteras på en webbplats för SharePoint-innehåll. 

> [!NOTE]
> Du måste ha till gång till en innehålls Center webbplats för att skapa en dokument modell eller för att använda en i ett SharePoint-dokumentbibliotek. 

Formulär bearbetnings modeller skapas i PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)men skapandet startas direkt från ett SharePoint-dokumentbibliotek. Skapande av formulär bearbetnings modeller måste aktive ras i dokument biblioteket för att en användare ska kunna skapa en formulär bearbetnings modell för det och en administratör kan göra detta i administratörs inställningarna för innehåll. För formulär bearbetnings modeller används PowerAutomate-flöden för att bearbeta filer när de överförs till dokument biblioteket.

När du skapar en dokument metod kan du skapa en ny [SharePoint-innehållstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) som sparas i galleriet för SharePoint-innehålls typer. Eller så kan du använda befintliga innehålls typer för att definiera modellen om det behövs.

Formulär bearbetnings modeller skapas i PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)men skapandet startas direkt från ett SharePoint-dokumentbibliotek. Skapande av formulär bearbetnings modeller måste aktive ras i dokument biblioteket för att en användare ska kunna skapa en formulär bearbetnings modell för den. Eller en administratör kan göra detta i innehålls förstå administratörs inställningarna. För formulär bearbetnings modeller används PowerAutomate-flöden för att bearbeta filer när de överförs till dokument biblioteket.

Formulär bearbetnings modeller skapar också nya [SharePoint-innehålls typer](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)och lagras även i galleriet SharePoint-innehålls typer.

## <a name="where-they-can-be-applied"></a>Var de kan användas

Du kan använda dokument för att förstå modeller för SharePoint-dokumentbibliotek som du har åtkomst till. Använd innehålls Center för att skapa en dokument förståelses modell och använda den i olika dokument bibliotek. I innehålls centret får du en mer Central kontroll för hur du kan använda dokument förståelse och var de används. OBS! den här informationen måste också lyfta fram ett innehålls Center.

Det går för närvarande bara att använda formulär bearbetnings modeller i SharePoint-dokumentbiblioteket som du skapade dem från. Detta gör det möjligt för licensierade användare att få åtkomst till webbplatsen att kunna skapa en modell för formulär bearbetning.

 ## <a name="see-also"></a>Se även
[Utbildning: förbättra företags prestanda med hjälp av AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Skapa en klassificerare](create-a-classifier.md)</br>
[Skapa en Extractor](create-an-extractor.md)</br>
[Använda en modell för dokument förståelse](apply-a-model.md)</br>
[Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)</br>
