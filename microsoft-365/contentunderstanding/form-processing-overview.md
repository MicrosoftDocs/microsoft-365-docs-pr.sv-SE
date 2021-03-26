---
title: Översikt av formulär bearbetning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Läs mer om formulärbearbetning i Microsoft SharePoint Syntex
ms.openlocfilehash: e3cf8298a2db9383e5b88dde737efc84e75c7f19
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222263"
---
# <a name="form-processing-overview"></a>Översikt av formulär bearbetning

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

I Microsoft SharePoint Syntex används formulärbearbetning i Microsoft PowerApps [AI Builder](/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.

Du kan använda formulärbearbetning i AI Builder för att skapa AI-modeller där maskininlärning används för att identifiera och extrahera nyckelvärdepar och tabelldata från strukturerade eller delvis strukturerade dokument, som formulär och fakturor.

Organisationer får ofta fakturor i stora kvantiteter från en mängd olika källor, t. ex. post, fax, e-post osv. Det kan ta lång tid att bearbeta dessa dokument och lägga till dem manuellt i en databas. Med formulärbearbetning automatiseras processen genom att AI används för att extrahera text, nyckel/värde-par och tabeller från dina dokument. 

> [!NOTE]
> Mer information om formulärbearbetning och scenarioexempel finns i [Införande av SharePoint Syntex: Kom igång-guide](./adoption-getstarted.md).

Du kan till exempel skapa en modell för formulärbearbetning som identifierar alla inköpsorder som laddas upp till dokumentbiblioteket. Från varje inköpsorder kan du extrahera och visa vissa data som är viktiga för dig, t. ex. *PO-nummer*, *datum* eller *summa*.

![Dokumentbiblioteksvy](../media/content-understanding/doc-lib-done.png)</br>  

Du använder exempelfiler för att träna modellen och definiera vilken information som ska extraheras från formuläret. Dokumentets layout registreras genom att modellen tränas. Du behöver bara fem formulärdokument för att komma igång. AI Builder analyserar dina exempelfiler för nyckel-värdepar och du kan även manuellt identifiera de som eventuellt inte har upptäckts.  Med AI Builder kan du testa din modells precision mot dina exempelfiler.

När du har tränat och publicerat modellen skapar modellen ett [Power Automate-flöde](/power-automate/getting-started). Flödet körs när en fil överförs till dokumentbiblioteket i SharePoint och hämtar data som har identifierats av modellen. Extraherade data visas i kolumner i modellens dokumentbiblioteksvy.

En Office 365-administratör måste [aktivera formulärbearbetning](./set-up-content-understanding.md) för SharePoint-dokumentbiblioteket för att användarna ska kunna [skapa en modell för formulärbearbetning](create-a-form-processing-model.md) i det. Du kan välja webbplatser under eller efter konfigurationen i dina hanteringsinställningar.

### <a name="file-limitations"></a>Filbegränsningar

När du använder formulärbearbetningsmodeller ska du observera [kraven och begränsningar för filanvändningen](/ai-builder/form-processing-model-requirements).

### <a name="multi-geo-environments"></a>Multi-Geo miljöer

När Du konfigurerar SharePoint Syntex i en [Microsoft 365 Multi-Geo-miljö](../enterprise/microsoft-365-multi-geo.md)kan du bara konfigurera den så att den använder formulärbearbetning på den centrala platsen. Om du vill använda formulärbearbetning på en lokal plats kontaktar du Microsofts support.






## <a name="see-also"></a>Se även
  
[Power Automate-dokumentation](/power-automate/)

[Skapa en modell för formulärbearbetning](create-a-form-processing-model.md)

[Översikt av dokumenttolkning](document-understanding-overview.md)

[Utbildning: Förbättra affärsprestanda med AI Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)