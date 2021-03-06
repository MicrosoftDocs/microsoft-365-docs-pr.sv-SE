---
title: Hantera undantag från automationsmappar
description: Lägg till undantag för automatiseringsmappar för att styra filer som är undantagna från en automatiserad undersökning.
keywords: hantera, automatisering, undantag, blockera, rensa, skadlig
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185843"
---
# <a name="manage-automation-folder-exclusions"></a>Hantera undantag från automationsmappar 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

Med undantag för automatiseringsmappar kan du ange mappar som automatisk undersökning ska hoppa över. 

Du kan kontrollera följande attribut om mappen som du vill hoppa över:
- Mappar 
- Filtillägg
- Filnamn


**Mappar**<br>
Du kan ange en mapp och dess undermappar som ska hoppas över. 


>[!NOTE]
>För närvarande stöds inte användning av jokertecken som ett sätt att utesluta filer i en katalog ännu. 


**Tillägg**<br>
Du kan ange tillägg som ska undantas i en viss katalog. Tilläggen är ett sätt att förhindra en attack från att använda en undantagen mapp för att dölja en sårbarhet. Tilläggen definierar uttryckligen vilka filer som ska ignoreras. 

**Filnamn**<br>
Du kan ange vilka filnamn som ska undantas i en viss katalog. Namnen är ett sätt att förhindra en attack från att använda en undantagen mapp för att dölja en sårbarhet. Namnen definierar uttryckligen vilka filer som ska ignoreras. 



## <a name="add-an-automation-folder-exclusion"></a>Lägga till ett undantag för automatiseringsmappar
1. Välj Undantaget för **automatiseringsmappen Inställningar**  >  **navigeringsfönstret.**  

2. Klicka **på Undantag för ny mapp.**  

3. Ange mappinformationen:

    - Mapp
    - Tillägg
    - Filnamn
    - Beskrivning
    

4. Klicka på **Spara**.

>[!NOTE]
> Kommandon i Live Response för att samla in eller undersöka uteslutna filer misslyckas och felmeddelandet: "Filen är undantagen". Dessutom ignorerar automatiska undersökningar uteslutna objekt.

## <a name="edit-an-automation-folder-exclusion"></a>Redigera ett undantag för automatiseringsmappar 
1. Välj Undantaget för **automatiseringsmappen Inställningar**  >  **navigeringsfönstret.** 

2. Klicka **på** Redigera för undantag för mappen.  

3. Uppdatera informationen om regeln och klicka på **Spara.**

## <a name="remove-an-automation-folder-exclusion"></a>Ta bort ett undantag för automatiseringsmappar 
1. Välj Undantaget för **automatiseringsmappen Inställningar**  >  **navigeringsfönstret.**  
2. Klicka på **Ta bort undantag.** 


## <a name="related-topics"></a>Relaterade ämnen
- [Hantera automatisering av tillåtna/blockerade listor](manage-indicators.md)
- [Hantera uppladdningar av automationsfil](manage-automation-file-uploads.md)
