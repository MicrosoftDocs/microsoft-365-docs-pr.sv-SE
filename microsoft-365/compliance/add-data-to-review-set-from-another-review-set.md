---
title: Lägga till data från en granskningsuppsättning i en annan granskningsuppsättning
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
description: Lär dig hur du väljer dokument från en granskningsuppsättning och arbetar med dem enskilt i en annan uppsättning Advanced eDiscovery fall.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161611"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>Lägga till data i en granskningsuppsättning från en annan granskningsuppsättning

I vissa fall kan det vara nödvändigt att välja dokument från en granskningsuppsättning och arbeta med dem enskilt i en annan granskningsuppsättning. Det här är särskilt användbart om du har tagit bort innehåll i en granskningsuppsättning och vill köra analyser på delmängden data.

Följ arbetsflödet i den här artikeln om du vill lägga till innehåll från en granskningsuppsättning till en annan.

## <a name="create-a-review-set"></a>Skapa en granskningsuppsättning

Innan du börjar måste du skapa en granskningsuppsättning där du kan lägga till data.  En ny granskningsuppsättning kan läggas till på **fliken Granska för** ärendet. Mer information finns i [Skapa en granskningsuppsättning](managing-review-sets.md#create-a-review-set).

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>Steg 1: Identifiera innehåll som du vill lägga till i en annan granskningsuppsättning

Du kan lägga till innehåll från en granskningsuppsättning till en annan genom att välja specifika dokument i källgranskningsuppsättningen eller genom att markera alla objekt som returneras av en granskningsuppsättningsfråga. Om du vill lägga till markerade objekt markerar du objekten, väljer **Åtgärd** och väljer sedan Lägg till **i en annan granskningsuppsättning**.

![Lägg till i en annan granskningsuppsättning i åtgärdsmenyn](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>Steg 2: Ange alternativ för att lägga till i en annan granskningsuppsättning

Välj den **granskningsuppsättning som du vill lägga** till objekt i på den utfällade sidan Lägg till i ytterligare granskningsalternativ. Välj om du vill **lägga till Alla sökresultat** eller Markerade **objekt**.  **Med ytterligare information** får du alternativ för att ta med alla  metadata från objekten och om du vill ta med taggarna (genom att markera kryssrutan Etiketter) från källgranskningsuppsättningen när dokumenten läggs till i den nya granskningsuppsättningen.  

![Alternativ för att lägga till data i en annan granskningsuppsättning](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

När du klickar **på Ok** skapas ett nytt jobb (med namnet Lägga till **data** i en annan granskningsuppsättning) för att lägga till innehållet i en annan granskningsuppsättning. Du kan gå till fliken **Jobb** och övervaka förloppet för det här jobbet. Mer information finns i [Hantera jobb.](managing-jobs-ediscovery20.md)
