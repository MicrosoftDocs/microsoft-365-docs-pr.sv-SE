---
title: Översikt av formulär bearbetning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Läs mer om formulärbearbetning i Microsoft SharePoint Syntex
ms.openlocfilehash: 9b5b9b1c54220037e1c10f2722a641b526592f84
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338619"
---
# <a name="form-processing-overview"></a>Översikt av formulär bearbetning

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

I Microsoft SharePoint Syntex används formulärbearbetning i Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.

Du kan använda formulärbearbetning i AI Builder för att skapa AI-modeller där maskininlärning används för att identifiera och extrahera nyckelvärdepar och tabelldata från strukturerade eller delvis strukturerade dokument, som formulär och fakturor.

Organisationer får ofta fakturor i stora kvantiteter från en mängd olika källor, t. ex. post, fax, e-post osv. Det kan ta lång tid att bearbeta dessa dokument och lägga till dem manuellt i en databas. Genom att använda AI för att extrahera text, nyckel/värdepar och tabeller från dina dokument utförs formulärbearbetningen automatiskt. 

> [!NOTE]
> Mer information om formulärbearbetning och scenarioexempel finns i [Införande av SharePoint Syntex: Kom igång-guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).

Du kan till exempel skapa en modell för formulärbearbetning som identifierar alla inköpsordrar som har laddats upp till dokumentbiblioteket. Från varje inköpsorder kan du extrahera och visa vissa data som är viktiga för dig, t. ex. *PO-nummer*, *datum* eller *summa*.

![Dokumentbiblioteksvy](../media/content-understanding/doc-lib-done.png)</br>  

Du kan också använda exempelfiler för att träna modellen och definiera vilken information som ska extraheras från formuläret. Dokumentets layout lärs in genom att modellen tränas och lär sig att extrahera data från liknande platser i dina formulär eftersom de har en liknande layout med liknande struktur. 

Du behöver minst fem formulärdokument för att komma igång. AI Builder analyserar dina exempelfiler för nyckel-värdepar och identifierar sedan manuellt de som eventuellt inte har identifierats.  Med AI Builder kan du testa din modells precision mot dina exempelfiler.

När du har tränat och publicerat modellen kan du använda den för att skapa ett [Power Automate-flöde](https://docs.microsoft.com/power-automate/getting-started) som körs när en fil laddats upp till dokumentbiblioteket i SharePoint. Därefter extraheras de data som har identifierats i modellen. Extraherade data visas i kolumner i modellens dokumentbiblioteksvy.

Du använder exempelfiler för att träna modellen och definiera vilken information som ska extraheras från formuläret. Dokumentets layout registreras genom att modellen tränas. Du behöver bara fem formulärdokument för att komma igång. AI Builder analyserar dina exempelfiler för nyckel-värdepar och du kan även manuellt identifiera de som eventuellt inte har upptäckts.  Med AI Builder kan du testa din modells precision mot dina exempelfiler.

När du har tränat och publicerat modellen skapar modellen ett [Power Automate-flöde](https://docs.microsoft.com/power-automate/getting-started). Flödet körs när en fil överförs till dokumentbiblioteket i SharePoint och hämtar data som har identifierats av modellen. Extraherade data visas i kolumner i modellens dokumentbiblioteksvy.

En Office 365-administratör måste [aktivera formulärbearbetning](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) för SharePoint-dokumentbiblioteket för att användarna ska kunna [skapa en modell för formulärbearbetning](create-a-form-processing-model.md) i det. Du kan välja webbplatser under eller efter konfigurationen i dina hanteringsinställningar.



## <a name="see-also"></a>Se även
  
[Power Automate-dokumentation](https://docs.microsoft.com/power-automate/)

[Skapa en modell för formulärbearbetning](create-a-form-processing-model.md)

[Översikt av dokumenttolkning](document-understanding-overview.md)

[Utbildning: Förbättra affärsprestanda med AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
