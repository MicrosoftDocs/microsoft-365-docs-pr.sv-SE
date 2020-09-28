---
title: Översikt över formulär bearbetning
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
description: Lär dig mer om formulär bearbetning i Microsoft SharePoint Syntex
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295182"
---
# <a name="form-processing-overview-preview"></a>Översikt över formulär bearbetning (för hands version)

Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

Project cortex använder Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.

Du kan använda hjälp av AI Builder för att skapa AI-modeller som använder maskin Learning Technology för att identifiera och extrahera nyckelord och tabell data från strukturerade eller halv strukturerade dokument, till exempel formulär och fakturor.

Använd AI Builder-blanketten för att skapa AI-modeller som utnyttjar Machine Learning (ML)-teknik för att identifiera och extrahera nycklar och värde-par och tabell data från strukturerade eller halv strukturerade dokument, till exempel formulär och fakturor.

Organisationer tar ofta emot fakturor i stora mängder från en mängd olika källor, till exempel e-post, Fax, e-post, etc. Det kan ta en lång stund att bearbeta dessa dokument och ange dem manuellt i en databas. Genom att använda AI för att extrahera text, viktiga par och tabeller från dokumenten, bearbetar formulär bearbetningen den här processen. 

Du kan till exempel skapa en modell för formulär bearbetning som identifierar alla inköps order dokument som laddas upp till dokument biblioteket. Från varje inköps order kan du extrahera och visa specifika data som är viktiga för dig, till exempel *inköps order nummer*, *datum*eller *Total kostnad*.

Du kan också använda exempelfiler för att träna modellen och ange vilken information som ska extraheras från formuläret. Layouten i dokumentet bevaras genom att öva på modellen. Du behöver minst fem formulär dokument för att komma igång. AI-byggnaden analyserar exempelfilerna efter par av nycklar och värden, och sedan identifieras de som inte har identifierats manuellt.  Med hjälp av AI-verktyget kan du testa korrektheten hos dina exempelfiler.

När du har tränat och publicerat modellen kan du använda den för att skapa ett [energi](https://docs.microsoft.com/power-automate/getting-started) spår som körs efter att en fil har laddats upp till SharePoint-dokumentbiblioteket. Då extraheras data som har identifierats i modellen. Extraherade data visas i kolumner i modellens dokument bibliotek.

Du använder exempelfiler för att träna modellen och ange vilken information som ska extraheras från formuläret. Layouten i dokumentet bevaras genom att öva på modellen. Du behöver bara fem formulär dokument för att komma igång. AI-verktyget analyserar exempelfilerna för par med nyckelord och du kan också manuellt identifiera dem som eventuellt inte har identifierats.  Med hjälp av AI-verktyget kan du testa korrektheten hos dina exempelfiler.

När du tränar och publicerar modellen kan du använda den för att skapa ett [energi](https://docs.microsoft.com/power-automate/getting-started)spår. Flödet körs när en fil laddas upp till SharePoint-dokumentbiblioteket och extraherar data som har identifierats i modellen. Extraherade data visas i kolumner i modellens dokument bibliotek.

En 365 Office-administratör måste [Aktivera formulär bearbetning](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) för att användare ska kunna [skapa en modell för formulär bearbetning](create-a-form-processing-model.md) i SharePoint-dokumentbiblioteket.

## <a name="see-also"></a>Se även
  
[Automatiserad energi dokumentation](https://docs.microsoft.com/power-automate/)</br>
[Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)</br>
[Översikt över dokument förståelse](document-understanding-overview.md)</br>
[Utbildning: förbättra företags prestanda med hjälp av AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
