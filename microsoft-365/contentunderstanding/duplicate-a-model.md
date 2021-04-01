---
title: Duplicera en modell i Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Lär dig hur och varför du duplicerar en modell i Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446083"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a>Duplicera en modell i Microsoft SharePoint Syntex

Att skapa en dokumenttolkningsmodell kan spara tid och arbete om du behöver skapa en ny modell och vet att en befintlig modell liknar den du behöver.

Till exempel klassificerar en befintligt modell med namnet ”Kontrakt” samma filer som du behöver arbeta med. Den nya modellen extraherar en del av befintliga data men måste uppdateras för att extrahera ytterligare data. I stället för att skapa och träna en ny modell från grunden kan du använda funktionen för att duplicera modeller för att göra en kopia av Kontrakt-modellen, vilket också kommer kopiera alla associerade träningsobjekt, som exempelfiler och entitetsextraktorer.

När du duplicerar modellen kan du efter att du bytt namn på den (till exempel till ”Kontraktförnyelser”) göra uppdateringar på den. Du kan till exempel välja att ta bort vissa av de befintliga extraherade fälten som du inte behöver och sedan träna modellen att extrahera ett nytt (till exempel ”Förnyelsedatum”).

## <a name="duplicate-a-model"></a>Duplicera en modell

Följ dessa steg för att duplicera en dokumenttolkningsmodell.

1. I innehållscentret väljer du **Modeller** för att visa listan med modeller.

2. På sidan **Modeller** väljer du den modell du vill duplicera.

3. Genom att använda menyfliksområdet eller knappen **Visa åtgärder** (bredvid modellnamnet) väljer du **Duplicera**.</br>

    ![Skärmbild av sidan Modeller som visar en vald modell med alternativen för Duplicera markerade.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. På panelen **Duplicera modell**:

   a. Under **Namn** anger du det nya namnet på modellen som du vill duplicera.</br>

    ![Skärmbild som visar panelen Duplicera modell.](../media/content-understanding/duplicate-model-panel.png) </br>

   b. Under **Beskrivning** lägger du till en beskrivning för den nya modellen.

   c. (Valfritt) Under **Avancerade inställningar** väljer du om du vill associera en befintlig [innehållstyp](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).

5. Välj **Duplicera**.

## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)

[Byt namn på en modell](rename-a-model.md)

[Skapa en extraktor](create-an-extractor.md)

[Översikt av dokumenttolkning](document-understanding-overview.md)

[Förklaringstyper](explanation-types-overview.md)

[Använda en modell](apply-a-model.md) 

[Tillgänglighetsläge för SharePoint Syntex](accessibility-mode.md)