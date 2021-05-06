---
title: Konfigurera smarta etiketter i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Med smarta etiketter kan du använda maskininlärningsfunktionerna när du granskar innehåll i Advanced eDiscovery fall. Använd smarta märkningsgrupper för att visa resultatet av modeller för maskininlärning, till exempel modellen för juristklientprivilegier.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "52161503"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Konfigurera smarta etiketter i Advanced eDiscovery

Maskininlärningsfunktionerna (ML) i Advanced eDiscovery kan hjälpa dig att effektivisera beslutsprocessen när du granskar ärendedokument i en uppsättning med granskning. Smarta etiketter är ett sätt att ta ML de funktioner som ingår i beslutet: när du taggar dokument under granskning. När du skapar en grupp för smarta etiketter visas de beslut som är resultatet av den ML-modell som du har kopplat till gruppen för smarta etiketter i linje med taggarna i tagggruppen. På så sätt kan ML se resultatinformationen i linje när du granskar specifika dokument.

## <a name="how-to-set-up-a-smart-tag-group"></a>Konfigurera en grupp för smarta etiketter

1. I en granskningsuppsättning klickar du **på Hantera granskningsuppsättning** och sedan på **Hantera taggar**.

2. Klicka **på Lägg till tagggrupp** och välj sedan Lägg till grupp för smarta **etiketter.**

3. Välj ML modell som du vill koppla till tagggruppen.
    
   Då skapas en tagggrupp och *N* underordnade taggar, *där N* är antalet möjliga utdata för modellen. Modellen för identifiering av [behörigheter för juristklienter](attorney-privilege-detection.md) har till exempel två möjliga utdata: 

   - **Positivt** – används för att tagga dokument som innehåller innehåll som är behörig att göra en juristklient.
   
   - **Negativ** – används för att tagga dokument som inte innehåller innehåll som är behörig att göra med jurister.
    
    Om du väljer den här modellen skapas en tagggrupp med  två underordnade taggar (en underordnad tagg med namnet Positivt och den andra med namnet **Negativ**) för granskningsuppsättningen. I det här exemplet motsvarar varje underordnad tagg något av de möjliga resultaten från modellen för identifiering av behörigheter för juristklienter.

4. Du kan också byta namn på tagggruppen och underordnade taggar. Du kan till exempel byta namn på **taggen Positiv** till **Privilegierad** och **Negativ till** **Inte behörig.**

## <a name="how-to-use-smart-tags"></a>Så här använder du smarta etiketter

När du granskar ett dokument visas modellens resultat bredvid lämplig underordnad tagg. Om du till exempel har en smart etikettgrupp för identifiering av juristklientbehörighet och du granskar ett dokument som kan vara privilegierat visas orsaken till den slutsatsen bredvid motsvarande tagg. Det är viktigt att observera att taggen inte tillämpas automatiskt i dokumentet. Granskaren kan fatta ett beslut om hur dokumentet ska tagga.
