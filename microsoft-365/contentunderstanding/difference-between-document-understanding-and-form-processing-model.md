---
title: Skillnader mellan modeller för dokumenttolkning och modeller för formulärbearbetning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Beskriver viktiga skillnader mellan modeller för dokumenttolkning och modeller för formulärbearbetning
ms.openlocfilehash: 5fa9bd6b5873a11c00b19663226c4e3dd2b65825
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321791"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Skillnader mellan modeller för dokumenttolkning och modeller för formulärbearbetning 


Med innehållstolkning i Microsoft SharePoint Syntex kan du identifiera och klassificera dokument som har laddats upp till SharePoints dokumentbibliotek och genom att extrahera relevant information från varje fil.  När filer till exempel överförs till ett dokumentbibliotek i SharePoint kan alla filer som identifieras som *Inköpsordrar* klassificeras som sådana och sedan visas i en anpassad vy för dokumentbiblioteket. Du kan också hämta särskild information från varje fil (till exempel *Inköpsordernummer* och *Summa*) och visa den som en kolumn i vyn för dokumentbiblioteket. 

Med innehållstolkning kan du skapa *modeller* för att identifiera och hämta den information du behöver. Modeller har ett värde som hjälper dig att lösa affärsproblem för sökningar, affärsprocesser, regelefterlevnad och många andra.

Det finns två modell typer som du kan använda:

- [Modeller för dokumenttolkning](document-understanding-overview.md)
- [Modeller för formulärbearbetning](form-processing-overview.md)

Båda modellerna används vanligtvis för samma syfte och de viktigaste skillnaderna som anges nedan påverkar vilka som du kan använda.



## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Strukturerat jämfört med ostrukturerat och halvstrukturerat innehåll

Använd modeller för dokumenttolkning till att identifiera och hämta data från ostrukturerade dokument, till exempel brev eller kontrakt, där de textenheter som du vill extrahera finns i meningar eller i vissa områden i dokumentet. Ett ostrukturerat dokument kan till exempel vara ett avtal om förnyelse som kan skrivas ut på olika sätt. Informationen finns dock konsekvent i brödtexten i varje avtal om förnyelse, till exempel textsträngen *tjänstens startdatum* följt av ett faktiskt datum.   

Använd modeller för formulärbearbetning för att identifiera filer och hämta data från strukturerade eller halvstrukturerade dokument, t. ex. formulär och fakturor. Modeller för formulärbearbetning är utbildade för att förstå layouten av ditt formulär från t. ex. dokument och lär sig att leta efter de data du behöver extrahera från liknande platser, eftersom formulär har en mer strukturerad layout där enheterna finns på samma plats (t. ex. ett personnummer i en skatteformulär). 

> [!NOTE]
> För att skapa en modell för dokumenttolkning eller för att använda den i ett dokumentbibliotek i SharePoint måste du ha tillgång till en webbplats för innehållscenter. 


## <a name="where-they-are-created"></a>Var de skapas

Modeller för dokumenttolkning skapas och hanteras på en SharePoint-webbplats för innehållscenter. 

> [!NOTE]
> Mer information om indatafiler finns i [Krav och begränsningar för modeller för formulärbearbetning](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

Modeller för formulärbearbetning skapas i PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), men skapandet startas direkt från ett dokumentbibliotek i SharePoint. Skapande av modell för formulärbearbetning måste aktiveras för ditt dokumentbibliotek för att en användare ska kunna skapa en modell för formulärbearbetning för den och en administratör kan göra detta i administratörsinställningar för innehållstolkningn. Modeller för formulärbearbetning använder PowerAutomate-flöden för att bearbeta filer när de överförs till dokumentbiblioteket.

När du skapar en modell för dokumenttolkning skapar du en ny [innehållstyp för SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) som sparas i galleriet för innehållstyper i SharePoint. Du kan också använda befintliga innehållstyper för att definiera din modell om det behövs.

Modeller för formulärbearbetning skapas i PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), men skapandet startas direkt från ett dokumentbibliotek i SharePoint. Skapande av modellen för formulärbearbetning måste aktiveras i dokumentbiblioteket för att en användare ska kunna skapa en modell för formulärbearbetning för den. Eller så kan en administratör göra detta i administratörsinställningar för innehållstolkning. Modeller för formulärbearbetning använder PowerAutomate-flöden för att bearbeta filer när de överförs till dokumentbiblioteket.

Modeller för formulärbearbetning skapar också nya [innehållstyper för SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) och lagras även i galleriet för innehållstyper i SharePoint.

## <a name="where-they-can-be-applied"></a>Var de kan användas

Du kan använda modeller för dokumenttolkning för dokumentbibliotek i SharePoint som du har åtkomst till. Använd innehållscentret för att skapa en modell för dokumenttolkning och använd det i olika dokumentbibliotek. I innehållscentret får du en mer central kontroll för hur modeller för dokumenttolkning används och var de används. OBS! den här informationen måste också sammanställas till ett innehållscenter.

Modeller för formulärbearbetning kan för närvarande bara användas för dokumentbiblioteket i SharePoint som du skapade dem från. Det gör att licensierade användare med åtkomst till webbplatsen kan skapa en modell för formulärbearbetning. Observera att din administratör måste aktivera formulärbearbetning i ett dokumentbibliotek i SharePoint för att den ska vara tillgänglig för licensierade användare.

 ## <a name="see-also"></a>Se även
[Utbildning: Förbättra affärsprestanda med AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)

[Skapa en klassificerare](create-a-classifier.md)

[Skapa en extraherare](create-an-extractor.md)

[Använda en modell för dokumenttolkning](apply-a-model.md)

[Skapa en modell för formulärbearbetning](create-a-form-processing-model.md)
