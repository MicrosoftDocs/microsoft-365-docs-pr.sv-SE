---
title: Prediktiv kodningsmodul för Advanced eDiscovery (förhandsversion)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Den nya prediktiv kodningsmodulen i Advanced eDiscovery använder maskininlärning för att analysera dokument i en granskningsuppsättning för att förutsäga vilka dokument som är relevanta för ditt ärende eller undersökning.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162538"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>Prediktiv kodningsmodul för Advanced eDiscovery (förhandsversion)

Med den nya prediktiv kodningsmodulen i Advanced eDiscovery kan du skapa och skapa en modell för att prioritera granskning av dokument med början i de mest relevanta dokumenten. För att komma igång kan du skapa en modell, märka upp till 50 dokument och sedan filtrera dokument efter resultat från modellförutsägelse för att granska relevanta dokument som inte är relevanta.

Här är en snabb överblick av arbetsflödet:

1. Öppna modulen prediktiv kodning i en granskningsuppsättning.

   ![Klicka på listrutan Analysera i en granskning för att gå till modulen Prediktiv kodning](..\media\PredictiveCoding1.png)

2. På sidan **Prediktiv kodningsmodeller** klickar du **på Ny modell för** att skapa en ny prediktiv kodningsmodell.

   ![Skapa en ny modell](..\media\PredictiveCoding2.png)

3. Ange minst 50 dokument som **relevanta** eller **Inte relevanta.** Etiketten används för att träna systemet.

   ![Ange att dokument ska vara relevanta eller inte relevanta för att utbilda systemet](..\media\PredictiveCoding3.png)

4. Använd filtret **Förutsägelseresultat** för modellen i granskningsuppsättningen. Gör så här:

   1. Klicka på Filter i **granskningsuppsättningen.**
   2. På den **utfällna** sidan Filter expanderar du avsnittet  **Analys/ML** och väljer sedan kryssrutan Prognosresultat för den modell som du vill använda.
   3. I filtret **Förutsägelseresultat** anger du ett prognosresultat. Filtret visar dokumenten i granskningsuppsättningen som matchar prognosresultatet.

      ![Ange ett resultat för förutsägelse för att filtrera dokument](..\media\PredictiveCoding4.png)

5. Övervaka modellens prestanda, status och stabilitet.

   ![Övervaka prestanda, status och stabilitet för din modell](..\media\PredictiveCoding5.png)
