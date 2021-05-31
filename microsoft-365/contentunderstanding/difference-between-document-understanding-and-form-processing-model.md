---
title: Skillnader mellan modeller för dokumenttolkning och modeller för formulärbearbetning
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauriellis
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Beskriver viktiga skillnader mellan modeller för dokumenttolkning och modeller för formulärbearbetning
ms.openlocfilehash: f19017ce8b748644177ac00f4daf7cb29ad522c6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706516"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Skillnader mellan modeller för dokumenttolkning och modeller för formulärbearbetning 

Med innehållstolkning i Microsoft SharePoint Syntex kan du identifiera och klassificera dokument som har laddats upp till SharePoints dokumentbibliotek och extrahera relevant information från varje fil.  När filer till exempel överförs till ett dokumentbibliotek i SharePoint kan alla filer som identifieras som *Inköpsordrar* klassificeras som sådana och sedan visas i en anpassad vy för dokumentbiblioteket. Du kan också hämta särskild information från varje fil (till exempel *Inköpsordernummer* och *Summa*) och visa den som en kolumn i vyn för dokumentbiblioteket. 

Med innehållstolkning kan du skapa *modeller* för att identifiera och hämta den information du behöver. Modeller har ett värde som hjälper dig att lösa affärsproblem för sökningar, affärsprocesser, regelefterlevnad och många andra.

Det finns två modell typer som du kan använda:

- [Modeller för dokumenttolkning](document-understanding-overview.md)
- [Modeller för formulärbearbetning](form-processing-overview.md)

Båda modellerna används vanligtvis för samma syfte och de viktigaste skillnaderna som anges nedan påverkar vilka som du kan använda.

> [!NOTE]
> Mer information om formulärbearbetning och scenarioexempel på dokumenttolkning finns i [Införande av SharePoint Syntex: kom igång-guide](./adoption-getstarted.md).

## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Strukturerat jämfört med ostrukturerat och halvstrukturerat innehåll

Använd modeller för dokumenttolkning till att identifiera och hämta data från ostrukturerade dokument, till exempel brev eller kontrakt, där de textenheter som du vill extrahera finns i meningar eller i vissa områden i dokumentet. Ett ostrukturerat dokument kan till exempel vara ett avtal om förnyelse som kan skrivas ut på olika sätt. Informationen finns dock konsekvent i brödtexten i varje avtal om förnyelse, till exempel textsträngen *tjänstens startdatum* följt av ett faktiskt datum.

Använd formulärbearbetning för att identifiera filer och extrahera data från strukturerade eller halvstrukturerade dokument som exempelvis formulär eller fakturor. Modeller för formulärbearbetning är utbildade för att förstå layouten av ditt formulär från exempeldokument och lär sig att leta efter de data du behöver extrahera från liknande platser. Formulär har oftast en mer strukturerad layout där enheterna finns på samma plats (till exempel ett personnummer i en skatteformulär).

> [!NOTE]
> För att skapa en modell för dokumenttolkning eller för att använda den i ett dokumentbibliotek i SharePoint måste du ha tillgång till en webbplats för innehållscenter. 

## <a name="where-models-are-created"></a>Var modellerna skapas

Modeller för dokumenttolkning skapas och hanteras på en SharePoint-webbplats för innehållscenter. 

> [!NOTE]
> Mer information om indatafiler finns i [Krav och begränsningar för modeller för formulärbearbetning](/ai-builder/form-processing-model-requirements). 

Modeller för formulärbearbetning skapas i PowerApps [AI Builder](/ai-builder/overview), men skapandet startas direkt från ett dokumentbibliotek i SharePoint. Ett dokumentbibliotek måste ha en modell för formulärbearbetning aktiverad för att en användare ska kunna skapa en modell för formulärbearbetning för den. Administratörer kan aktivera skapande av modell för formulärbearbetning i de administratörsinställningar som gäller för innehållstolkning. Modeller för formulärbearbetning använder PowerAutomate-flöden för att bearbeta filer när de överförs till dokumentbiblioteket.

När du skapar en modell för dokumenttolkning skapar du en ny [innehållstyp för SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) som sparas i galleriet för innehållstyper i SharePoint. Du kan också använda befintliga innehållstyper för att definiera din modell om det behövs.

Modeller för formulärbearbetning skapar också nya [innehållstyper för SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) och lagras även i galleriet för innehållstyper i SharePoint.

## <a name="where-they-can-be-applied"></a>Var de kan användas

Du kan använda modeller för dokumenttolkning för dokumentbibliotek i SharePoint som du har åtkomst till. Använd innehållscentret för att skapa en modell för dokumenttolkning och använd det i olika dokumentbibliotek. I innehållscentret får du en mer central kontroll för hur modeller för dokumenttolkning används och var de används. OBS! den här informationen måste också sammanställas till ett innehållscenter.

Modeller för formulärbearbetning kan för närvarande bara användas för dokumentbiblioteket i SharePoint som du skapade dem från. Det gör att licensierade användare med åtkomst till webbplatsen kan skapa en modell för formulärbearbetning. Observera att en administratör måste aktivera formulärbearbetning i ett dokumentbibliotek i SharePoint för att den ska vara tillgänglig för licensierade användare.

## <a name="comparison-of-forms-processing-and-document-understanding"></a>Jämförelse av formulärbearbetning och dokumenttolkning

Använd följande tabell för att förstå när du ska använda formulärbearbetning och när du ska använda dokumentförståelse:

| Funktion | Formulärbearbetning | Dokumenttolkning |
| ------- | ------- | ------- |
| Modelltyp – när du ska använda vilken | Används för halvstrukturerade filformat, till exempel PDF-filer för formulärinnehåll som fakturor och inköpsorder där layout och formatering är liknande.  | Används för halvstrukturerade filformat, till exempel Office-dokument där det finns skillnader i layouten men fortfarande är liknande information som ska extraheras. |
| Modellgenerering | Modell skapad i AI builder med smidig åtkomst från SharePoints dokumentbibliotek.| Modell skapad i SharePoint på nya webbplatsen för innehållscentret. |
| Klassificeringstyp| Inställbar klassificerare används för att ge ledtrådar till systemet om vilken data som ska extraheras.| Klassificerare som kan tränas med valfria extraktorer med maskininlärning för att tilldela dokumentplats angående vilken data som ska extraheras.|
| Platser | Tränad för ett enkelt dokumentbibliotek.| Kan tillämpas på flera bibliotek.|
| Filtyper som stöds| Träna på PDF-, JPG- och PNG-format, totalt 50 MB och 500 sidor.| Träna på 5-10 PDF-, Office- eller e-postfiler, inklusive negativa exempel.<br>Office-filer trunkeras till 64 000 tecken. OCR-skannade filer är begränsade till 20 sidor.|
| Integrera med hanterade metadata | Nej | Ja, genom att träna entitetsextraktorn till att referera till ett konfigurerat hanterat metadatafält.|
| Funktionen för efterlevnad integreras när Microsoft Information Protection är aktiverad. | Ställ in publicerade kvarhållningsetiketter.<br>Ställ in känslighetsetiketter är på väg. | Ställ in publicerade kvarhållningsetiketter.<br>Ställ in publicerade känslighetsetiketter. |
| Regioner som stöds| Formulärbearbetning är beroende av Power Platform. Information om global tillgänglighet för Power Platform och AI Builder se [ tillgängligheten för Power Platform](https://dynamics.microsoft.com/geographic-availability/). | Tillgängligt i alla regioner.|
| Transaktionskostnad | Använder AI Builder-krediter.<br>Krediter kan köpas i omgångar om 1 miljon.<br>1 miljon krediter ingår när över 300 SharePoint Syntex-licenser köps.<br>1 miljon krediter ger möjlighet till bearbetning av 2 000 filsidor.<br>| Uppgift saknas |
| Kapacitet | Använder standardmiljön för Power Platform (Anpassade miljöer med Dataverse-databas stöds) | Har inga kapacitetsbegränsningar.|
| Språk som stöds| Engelska <br>Kommer senare under 2021: Språk med latinska alfabet | Modellerna fungerar på alla språk med latinska alfabetet. Förutom Engelska: tyska, svenska, franska, spanska, italienska och portugisiska.|

## <a name="see-also"></a>Se även
[Utbildning: Förbättra affärsprestanda med AI Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Översikt för dokumenttolkning](document-understanding-overview.md)

[Översikt för formulärbearbetning](form-processing-overview.md)

[Introduktion till SharePoint Syntex](index.md)