---
title: Hantera undantag för automatiseringsmappar
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
ms.openlocfilehash: fb398f1acbea4bd8f388c072f9706f9b2ca25175
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070194"
---
# <a name="manage-automation-folder-exclusions"></a>Hantera undantag för automatiseringsmappar 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
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
1. I navigeringsfönstret väljer du Undantag **för mappar** i  >  **Inställningar automation.**  

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
1. I navigeringsfönstret väljer du Undantag **för mappar** i  >  **Inställningar automation.** 

2. Klicka **på** Redigera för undantag för mappen.  

3. Uppdatera informationen om regeln och klicka på **Spara.**

## <a name="remove-an-automation-folder-exclusion"></a>Ta bort ett undantag för automatiseringsmappar 
1. I navigeringsfönstret väljer du Undantag **för mappar** i  >  **Inställningar automation.**  
2. Klicka på **Ta bort undantag.** 


## <a name="related-topics"></a>Relaterade ämnen
- [Hantera automatisering av tillåtna/blockerade listor](manage-indicators.md)
- [Hantera uppladdningar av automatiseringsfiler](manage-automation-file-uploads.md)
