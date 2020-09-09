---
title: Översikt över formulär bearbetning (för hands version)
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
description: Lär dig mer om formulär bearbetning i Project cortex.
ms.openlocfilehash: 44ae5d9cbfbabc5615a751dba5f6c13290fc7b35
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405635"
---
# <a name="form-processing-overview-preview"></a>Översikt över formulär bearbetning (för hands version)
> [!Note]
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

Project cortex använder Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.
Du kan använda hjälp av AI Builder för att skapa AI-modeller som använder maskin Learning Technology för att identifiera och extrahera nyckelord och tabell data från strukturerade eller halv strukturerade dokument, till exempel formulär och fakturor.

Företag tar ofta emot fakturor i stora mängder och från en mängd olika källor, till exempel e-post, Fax, e-post eller personligen. Det kan ta en avsevärd tid att bearbeta dessa dokument och ange dem manuellt i databasen. Genom att använda AI för att extrahera text, viktiga par och tabeller från dina dokument automatiserar formulär bearbetning den processen. 

Du kan till exempel skapa en modell för formulär bearbetning som identifierar alla inköps order dokument som laddas upp till dokument biblioteket. Och från varje inköps order kan du extrahera och visa specifika data som är viktiga för dig, till exempel *inköps order nummer*, *datum*eller *totalkostnad*.

Du använder exempel filer för att träna modellen och ange vilken information som ska extraheras från formuläret. Layouten i dokumentet bevaras genom att öva på modellen. Du behöver bara fem formulär dokument för att komma igång. AI Builder analyserar dina exempel filer för par med nyckelord och du kan också manuellt identifiera dem som eventuellt inte har identifierats.  Med hjälp av AI-verktyget kan du testa korrektheten hos dina exempelfiler.

När du tränar och publicerar modellen kan du använda den för att skapa ett [energi](https://docs.microsoft.com/power-automate/getting-started)spår. Flödet körs när en fil laddas upp till SharePoint-dokumentbiblioteket och extraherar data som har identifierats i modellen. Extraherade data visas i kolumner i modellens dokument bibliotek.

En 365 Office-administratör måste [Aktivera formulär bearbetning](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) för att användare ska kunna [skapa en modell för formulär bearbetning](create-a-form-processing-model.md) i SharePoint-dokumentbiblioteket.



## <a name="see-also"></a>Se även
  
[Automatiserad energi dokumentation](https://docs.microsoft.com/power-automate/)</br>
[Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)</br>
[Översikt över dokument förståelse](document-understanding-overview.md)</br>
[Utbildning: förbättra företags prestanda med hjälp av AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




