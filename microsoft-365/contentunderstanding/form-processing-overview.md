---
title: Översikt över formulärbearbetning (förhandsgranskning)
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
description: Läs mer om formulärbearbetning i Project Cortex.
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540064"
---
# <a name="form-processing-overview-preview"></a>Översikt över formulärbearbetning (förhandsgranskning)
> [!Note]
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

Project Cortex använder Microsoft PowerApps [AI Builder-formulärbearbetning](https://docs.microsoft.com/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.
Du kan använda AI Builder-formulärbearbetning för att skapa AI-modeller som använder maskininlärningsteknik för att identifiera och extrahera nyckelvärdespar och tabelldata från strukturerade eller halvstrukturerade dokument, till exempel formulär och fakturor.

Företag får ofta fakturor i stora mängder och från en mängd olika källor, till exempel post, fax, e-post eller personligen. Det kan ta lång tid att bearbeta dessa dokument och manuellt skriva in dem i databasen. Genom att använda AI för att extrahera text, nyckel/värde-par och tabeller från dina dokument automatiserar formulärbearbetningen den här processen. 

Du kan till exempel skapa en formulärbearbetningsmodell som identifierar alla inköpsorderdokument som överförs till dokumentbiblioteket. Och från varje inköpsorder kan du extrahera och visa specifika data som är viktiga för dig, till exempel *PO-nummer,* *Datum*eller *Total kostnad*.

Du använder exempelfiler för att träna din modell och definiera den information som ska extraheras från formuläret. Dokumentets layout lärs genom att din modell tränas. Du behöver bara fem formulärdokument för att komma igång. AI-byggnaden analyserar dina exempelfiler för nyckel-värde-par, och du kan också manuellt identifiera de som kanske inte har upptäckts.  Med AI-byggare kan du testa modellens noggrannhet på dina exempelfiler.

När du har tränat och publicerat modellen skapar du ett [Power Automate-flöde](https://docs.microsoft.com/power-automate/getting-started) som körs när en fil överförs till SharePoint-dokumentbiblioteket och extraherar data som har identifierats i modellen. De extraherade data visas i kolumner i modellens dokumentbiblioteksvy.

En Office 365-administratör måste [aktivera formulärbearbetning](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) för SharePoint-dokumentbiblioteket för att användare ska kunna [skapa en formulärbearbetningsmodell](create-a-form-processing-model.md) i det.



## <a name="see-also"></a>Se även
  
[Dokumentation för Power Automate](https://docs.microsoft.com/power-automate/)</br>
[Skapa en formulärbearbetningsmodell](create-a-form-processing-model.md)</br>
[Översikt över dokuments förståelse](document-understanding-overview.md)</br>
[Utbildning: Förbättra företagets resultat med AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




