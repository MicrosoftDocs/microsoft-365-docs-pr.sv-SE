---
title: Förhandsgranska resultaten från en eDiscovery-sökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Förhandsgranska ett exempel på resultaten från en innehållssökning eller en Core eDiscovery-sökning i Microsoft 365 Efterlevnadscenter.
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538595"
---
# <a name="preview-ediscovery-search-results"></a>Förhandsgranska eDiscovery-sökresultaten

När du har kört en innehållssökning eller en sökning som är kopplad till ett Core eDiscovery-ärende kan du förhandsgranska ett exempel på resultaten från sökningen. Genom att förhandsgranska objekten som returneras av sökfrågan kan du avgöra om sökningen returnerar de resultat som du hoppades på eller om du behöver ändra sökfrågan och köra sökningen igen.

Så här gör du för att förhandsgranska resultaten som returneras av en sökning:

1. I Microsoft 365 Efterlevnadscenter går du till sidan Innehållssökning eller till ett Core eDiscovery-ärende.

2. Välj Sök för att visa den utfällbara sidan.

3. Längst ned på den utfällbara sidan klickar du på **Granska exempel**.

   ![Klicka på Granska exempel på utfällbara sidan för att förhandsgranska resultat](../media/PreviewSearchResults1.png)

   En sida visas med ett exempel på sökresultaten.

4. Välj ett objekt om du vill visa dess innehåll i läsfönstret.

   ![Förhandsgranska objekt i läsfönstret](../media/PreviewSearchResults2.png)

   Observera att nyckelord från sökfrågan markeras när du förhandsgranskar objekt i föregående skärmbild.

## <a name="how-the-search-result-samples-are-selected"></a>Hur exempel på sökresultat väljs

Högst 1 000 slumpmässigt valda objekt är tillgängliga att förhandsgranska. Förutom att det finns slumpmässigt valda objekt som är tillgängliga för förhandsgranskning måste de också uppfylla följande villkor:

- Högst 100 objekt från en enskild innehållsplats (en postlåda eller en webbplats) kan förhandsgranskas. Det innebär att det kan finnas färre än 1 000 objekt tillgängliga för förhandsgranskning. Om du till exempel söker i fyra postlådor och sökningen returnerar 1 500 uppskattade objekt kommer bara 400 att vara tillgängliga för förhandsgranskning eftersom bara 100 objekt från varje postlåda kan förhandsgranskas.

- För postlådeobjekt är endast e-postmeddelanden tillgängliga att förhandsgranska. Objekt som uppgifter, kalenderobjekt och kontakter kan inte förhandsgranskas.

- För webbplatsobjekt är endast dokument tillgängliga att förhandsgranska. Det går inte att förhandsgranska objekt som mappar, listor eller bifogade filer i listor.

## <a name="file-types-supported-when-previewing-search-results"></a>Filtyper som stöds vid förhandsgranskning av sökresultaten

Du kan förhandsgranska de filtyper som stöds i förhandsgranskningsfönstret. Om filtypen inte stöds måste du ladda ned en kopia av filen till den lokala datorn (klicka på **Ladda ned originalobjektet**). För ASPX-webbsidor ingår URL-adressen för sidan, men du kanske inte har behörighet att komma åt sidan. Icke indexerade objekt inte är tillgängliga för förhandsgranskning.

Följande filtyper stöds och kan förhandsgranskas i sökresultatfönstret.
  
- .txt, .html, .mhtml

- .eml

- .doc, .docx, .docm

- .pptm, .pptx

- .pdf

Följande filbehållartyper stöds också. Du kan visa listan med filer i behållaren i förhandsgranskningsfönstret.
  
- .zip

- .gzip