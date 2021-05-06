---
title: Lägga till sökresultat i en granskningsuppsättning
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
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du lägger till sökresultat eller exempel från dessa sökresultat i Advanced eDiscovery med en uppsättning med fallgranskning.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "52161635"
---
# <a name="add-search-results-to-a-review-set"></a>Lägga till sökresultat i en granskningsuppsättning

När du är nöjd med resultatet av en sökning och du är redo att granska och analysera sökresultaten kan du lägga till dem i en granskningsuppsättning i ärendet. Om du kopierar ursprungliga data till granskningsuppsättningen underlättar du även gransknings- och analysprocessen, eftersom du får avancerade analysverktyg som identifiering av teman, identifiering av närdubbletter och identifiering av e-posttrådar. Du kan också lägga till data från Microsoft 365 andra datakällor i en granskningsuppsättning så att du kan granska dessa data utöver de data du samlar in från Microsoft 365.

När du lägger till resultatet av en sökning i en granskningsuppsättning  (granskningsuppsättningarna i ett ärende visas på fliken Granska uppsättningar) inträffar följande:

- Sökningen körs igen. Det innebär att de verkliga sökresultaten som kopierats till granskningsuppsättningen kan vara annorlunda än de uppskattade resultat som returnerades när sökningen senast körts.

- Alla objekt i sökresultatet kopieras från den ursprungliga datakällan i live-tjänsterna och kopieras till en säker Azure Storage plats i Microsoft-molnet.

- Alla objekt (inklusive innehåll och metadata) indexeras om så att alla data i granskningsuppsättningen är fullt sökbara under granskningen av ärendedata. Omindexering av data resulterar i genomgående och snabba sökningar när du söker i data i granskningen som angetts under ärendets undersökning.

- En fil som [](encryption.md) krypteras med en Microsoft-krypteringsteknik och bifogas i ett e-postmeddelande som returneras i sökresultaten dekrypteras när e-postmeddelandet och den bifogade filen läggs till i granskningsuppsättningen. Du kan granska och köra frågor för den dekrypterade filen i granskningsuppsättningen. Du måste ha tilldelats rollen RMS-dekrypterad för att kunna lägga till dekrypterade e-postbilagor i en granskningsuppsättning. Mer information finns i [Dekryptering i eDiscovery Microsoft 365 och eDiscovery-verktyg](ediscovery-decryption.md).

Om du vill lägga till data i  en granskningsuppsättning klickar du på en sökning på fliken Sökningar och sedan på Lägg till resultat att granska **på** den utfällade sidan.

Du kan lägga till i en befintlig granskningsuppsättning eller skapa en ny granskningsuppsättning.  Om du lägger till i en ny granskningsuppsättning anger du namnet och klickar sedan på Lägg **till för** att visa den utfällade sidan.

![Välja en granskningsuppsättning och konfigurera samlingsalternativ](../media/AeD_AddToReviewSet.png)

Att lägga till data i en granskningsuppsättning är en långvariga process. Den här processen omfattar insamling av objekt från de ursprungliga datakällorna i Microsoft 365 (till exempel från postlådor och webbplatser), kopiera dem till Azure Storage-platsen (den här kopieringsprocessen kallas även för *pågestion)* och sedan indexera om objekten. Du kan spåra förloppet på fliken **Jobb** eller på fliken **Sökningar** genom att övervaka statusen i kolumnen Tillagda **data för att granska den inställda** kolumnen. När granskningsuppsättningen är klar  klickar du på fliken Granska uppsättningar för ärendet och sedan på granskningsuppsättningen för att påbörja filtrering, granskning, taggning och export av data i granskningsuppsättningen.

## <a name="define-options-to-scope-your-collection-for-review"></a>Definiera alternativ för att begränsa samlingen för granskning

När du lägger till innehållet i en sökning i en befintlig eller ny granskningsuppsättning har du följande alternativ för hur du samlar in innehållet för granskning:

- **Ta med versioner SharePoint (beta)**: Använd det här alternativet om du vill aktivera samlingen av alla versioner av ett SharePoint-dokument enligt versionsbegränsningarna och sökparametrar för samlingen. Om du väljer det här alternativet ökar storleken på objekt som läggs till i granskningsuppsättningen avsevärt.

- **Alternativ för hämtning av konversationer:** Objekt som lagts till i granskningsuppsättningen aktiveras för trådade konversationer så att innehåll kan granskas i samband med konversationen fram och tillbaka. Mer information finns i Granska [konversationer i Advanced eDiscovery](conversation-review-sets.md).

- **Aktivera hämtning av moderna bifogade filer:** Använd det här alternativet om du vill inkludera moderna bifogade filer eller länkade filer i samlingen för ytterligare granskning. Mer information om sökbara egenskaper för moderna bifogade filer finns i Dokumentera [metadatafält i Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

## <a name="add-a-sample-to-a-review-set"></a>Lägga till ett urval i en granskningsuppsättning

Om du vill validera resultatet av en sökning mer noggrant innan du lägger till alla i en granskningsuppsättning kan du lägga till ett urval av sökresultaten i en granskningsuppsättning i stället för att lägga till allt.

Om du vill lägga till ett exempel i en granskningsuppsättning klickar du på en sökning på **fliken** Sökningar och klickar **på Exempel** på den utfällplande sidan. Välj **något av följande** alternativ på sidan Samplingsparametrar:

- **Konfidensnivå %** **och konfidensintervall %** – De objekt som läggs till i granskningsuppsättningen bestäms av de statistiska parametrar som du anger. Om du normalt använder en konfidensnivå och intervall när samplingsresultat, anger du dem i listrutorna. I annat fall använder du standardinställningarna.

- **Slumpmässigt exempel %** – Objekten som läggs till i granskningsuppsättningen baseras på ett slumpmässigt urval av det angivna procenttalet av det totala antalet objekt som returneras av sökningen.

När du har valt och konfigurerat något av de tidigare alternativen väljer du en granskningsuppsättning att lägga till exemplet i och klickar sedan på **Skicka**. Du kan spåra förloppet  på fliken Jobb  eller på fliken Sökningar genom att övervaka statusen i kolumnen Tillagda **data för att granska den inställda.**

## <a name="optical-character-recognition"></a>Optisk teckenläsning

När du lägger till sökresultat i en granskningsuppsättning extraherar optisk teckenläsning (OCR) i Advanced eDiscovery automatiskt text från bilder och inkluderar bildtexten med de data som lagts till i en granskningsuppsättning. Du kan visa den extraherade texten i textvisningsprogrammet för den valda bildfilen i granskningsuppsättningen. På så sätt kan du göra ytterligare granskning och analys av text i bilder. OCR stöds för lösa filer, e-postbilagor och inbäddade bilder. En lista över filformat som stöds för OCR finns i Filformat [som stöds i Advanced eDiscovery.](supported-filetypes-ediscovery20.md#image)

Du måste aktivera OCR-funktioner för varje ärende som du skapar i Advanced eDiscovery. Mer information finns i Konfigurera [sök- och analysinställningar.](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)
