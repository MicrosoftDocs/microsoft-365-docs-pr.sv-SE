---
title: Byt namn på en extraktor i Microsoft SharePoint Syntex.
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
description: Lär dig hur och varför du byter namn på en extraktor i Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446054"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>Byt namn på en extraktor i Microsoft SharePoint Syntex.

Förr eller senare kan du behöva byta namn på en extraktor om du vill referera till ett extraherat datafält med ett annat namn. Din organisation bestämmer sig till exempel för att ändra sina kontraktsdokument och refererar till "kunder" som "klienter" i sina dokument. Om du extraherade ett "Kund"-fält i modellen kan du välja att byta namn på det till "Klient".

När du synkroniserar din uppdaterade modell till ditt SharePoint-dokumentbibliotek ser du en ny Klientkolumn i dokumentbiblioteksvyn. Vyn behåller kolumnen "Kund" för tidigare aktivitet, men uppdaterar den nya kolumnen "Klient" för alla nya dokument som bearbetas av modellen. 

> [!IMPORTANT]
>  Se till att synkronisera den uppdaterade modellen med de dokumentbibliotek där du tidigare använt den för att det nya kolumnnamnet ska visas. 

## <a name="rename-an-extractor"></a>Byta namn på en extraktor

Följ dessa steg om du vill byta namn på en entitetsextraktor.

1. I innehållscentret väljer du **Modeller** för att visa listan med modeller.

2. På sidan **Modeller**, i kolumnen **Name**, väljer du den modell för vilken du vill byta namn på en extraktor.

3. Under **Entitetsextraktor** väljer du namnet på den extraktor som du vill byta namn på och väljer sedan **Byt namn**.</br>

    ![Skärmbild av avsnittet Entitetsextraktor med en vald extraktor med alternativet Byt namn markerat.](../media/content-understanding/entity-extractor-rename.png) </br>

4. På panelen **Byt namn på entitetsextraktorn**:

   a. Under **Nytt namn** anger du det nya namnet på extraktorn.</br>

    ![Skärmbild som visar panelen Entitetsextraktor.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   b. (Valfritt) Under **Avancerade inställningar** välj om du vill associera en befintlig webbplatskolumn.

5. Välj **Byt namn**.

## <a name="see-also"></a>Se även
[Skapa en extraherare](create-an-extractor.md)

[Skapa en klassificerare](create-a-classifier.md)

[Byt namn på en modell](rename-a-model.md)

[Förklaringstyper](explanation-types-overview.md)

[Använd termlagringstaxonomi vid skapande av extraktor](leverage-term-store-taxonomy.md)

[Översikt av dokumenttolkning](document-understanding-overview.md)

[Använda en modell](apply-a-model.md) 
