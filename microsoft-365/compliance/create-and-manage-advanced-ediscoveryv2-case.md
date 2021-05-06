---
title: Skapa och hantera Advanced eDiscovery ärenden i Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: I den här artikeln beskrivs hur du skapar och hanterar Advanced eDiscovery ärenden. Det första steget är att skapa ett ärende och börja använda Advanced eDiscovery funktioner.
ms.openlocfilehash: d0f63bca90945c3dfe13b08fa0f1d139da8a9189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161946"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Skapa och hantera ett Advanced eDiscovery ärende

När du Advanced eDiscovery och tilldelar behörigheter till [eDiscovery-hanterare](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) i organisationen som hanterar ärenden är nästa steg att skapa och hantera ett ärende.

Den här artikeln innehåller också en översikt över hur ärenden kan hanteras Advanced eDiscovery ett juridiskt ärende eller andra typer av undersökningar.

## <a name="create-a-case"></a>Skapa ett ärende

Så här skapar du ett ärende och lägger till medlemmar. Den användare som skapar ärendet läggs automatiskt till som medlem. Medlemmar i ärendet kan komma åt ärendet i Microsoft 365 och utföra Advanced eDiscovery uppgifter.

1. Gå till <https://compliance.microsoft.com> och logga in med autentiseringsuppgifterna för användarkontot som har tilldelats eDiscovery-behörigheter. Medlemmar i rollgruppen Organisationshantering kan också skapa Advanced eDiscovery ärenden.

2. I det vänstra navigeringsfönstret i Microsoft 365 kompatibilitetscenter klickar du på **Visa alla** och sedan på **eDiscovery > Advanced**.

3. På **Advanced eDiscovery** klickar du på **fliken Ärenden** och sedan på Skapa ett **ärende.**

4. På den **utfällbara sidan Nytt eDiscovery-ärende** ger du ärendet ett namn (obligatoriskt) och skriver ett alternativt ärendenummer och en beskrivning. Namnet på ärendet måste vara unikt inom organisationen.

5. Klicka **på Spara** för att skapa ärendet.

   Det nya ärendet skapas och **Inställningar** i det nya ärendet visas.

6. På panelen **& på** fliken **Inställningar** klickar du på **Markera** och sedan på **Uppdatera**.

7. Klicka **på Uppdatera**.

8. På sidan **Hantera detta ärende,** under Hantera **medlemmar, klickar du på** Lägg till **för** att lägga till medlemmar i ärendet.

9. I listan över personer markerar du kryssrutan bredvid namnen på de personer som du vill lägga till i ärendet. Som tidigare förklarats bör du se till att de personer som du lägger till i ärendet har tilldelats rätt eDiscovery-behörigheter.

10. När du har valt de personer som ska läggas till som medlemmar i ärendet klickar du på Lägg **till**.

11. Klicka på **Spara på sidan Hantera** det här ärendet för **att** spara den nya listan med ärendemedlemmar.

12. Klicka på **fliken** Start för att gå till startsidan för ärendet.

## <a name="manage-the-workflow"></a>Hantera arbetsflödet

Här är ett enkelt arbetsflöde som Advanced eDiscovery för att komma igång med att använda [eDiscovery-metoder.](advanced-ediscovery-edrm.md) I vart och ett av de här stegen kommer vi också att belysa Advanced eDiscovery funktioner som du kan utforska.

![Advanced eDiscovery arbetsflöde](../media/AeDWorkflow.png)

1. **[Lägg till](add-custodians-to-case.md) andrekterare och [icke-tilläggsdatakällor](non-custodial-data-sources.md) i ärendet.** När ett ärende har skapats är det första steget att lägga till målsare. En *vårdnadshavare är* en person som har administrativ kontroll över ett dokument eller en elektronisk fil som kan vara relevant för ärendet. Du kan dessutom lägga till datakällor som inte är kopplade till en viss användare men som kan vara relevanta för ärendet.

   Här är några saker som händer (eller som du kan göra) när du lägger till vårdnadshavare i ett ärende:

   - Data i den andres Exchange-postlåda, OneDrive-konto och alla Microsoft Teams- eller Yammer-grupper som den insikande medlemmen är medlem i kan "markeras" som följddata i det aktuella fallet.
  
   - Omindexerade data (genom en process som kallas *Avancerad indexering).* Det gör det lättare att söka efter den i nästa steg.
  
   - Du kan lägga ett förvaringsarknr på data i samma anda. Då bevaras data som kan vara relevanta för ärendet under undersökningen.
  
   - Du kan koppla andra datakällor till en användare (du kan t.ex. associera en SharePoint-webbplats eller Microsoft 365-grupp med en vårdnadshavare) så att dessa data kan indexeras om, placeras i förvaring och sökas, precis som data i den postlådan eller i OneDrive-kontot.

   - Du kan använda [arbetsflödet för kommunikation](managing-custodian-communications.md) i Advanced eDiscovery skicka ett meddelande om juridiskt förvaring till dokumenterare.

2. **[Samla in relevant innehåll från datakällor.](create-draft-collection.md)** När du har lagt till inbyggda datakällor och icke-förfallna datakällor i ett ärende kan du använda det inbyggda samlingsverktyget för att söka i dessa datakällor efter innehåll som kan vara relevant för ärendet. Du använder nyckelord, egenskaper [](building-search-queries.md) och villkor för att skapa sökfrågor som returnerar sökresultat med de data som troligen är relevanta för ärendet. Du kan också:

   - Visa [samlingsstatistik](collection-statistics-reports.md) som kan hjälpa dig att förfina resultatet i en samling.

   - Förhandsgranska ett urval av samlingen för att snabbt kontrollera om relevanta data hittas.

   - Ändra en fråga och kör samlingen igen.

3. **[Spara samlingen i en granskningsuppsättning](commit-draft-collection.md)**. När du har konfigurerat och verifierat att en sökning returnerar önskade data är nästa steg att lägga till sökresultatet i en granskningsuppsättning. När du lägger till data i en granskningsuppsättning kopieras objekt från den ursprungliga platsen till en säker Azure Storage plats. Data indexeras om igen för att optimera dem för genomgående och snabba sökningar vid granskning och analys av objekt i granskningsuppsättningen. Du kan också lägga till [icke-Office 365 data i en granskningsuppsättning](load-non-office-365-data-into-a-review-set.md).

   Det finns även en särskild typ av granskningsuppsättning som du kan lägga till data i, en så kallad uppsättning *för konversationsgranskning.* De här typerna av granskningsuppsättningar ger möjlighet att återskapa, granska och exportera trådade konversationer som de i Microsoft Teams. Mer information finns i Granska [konversationer i Advanced eDiscovery](conversation-review-sets.md).

4. **Granska och analysera data i en granskningsuppsättning**. Nu när data finns i en granskningsuppsättning kan du använda en mängd olika verktyg och funktioner för att visa och analysera ärendedata med målet att minska datauppsättningen till det som är mest relevant för det ärende du undersöker. Här är en lista över några verktyg och funktioner som du kan använda i den här processen.

   - [Visa dokument](view-documents-in-review-set.md). Det omfattar att visa metadata för varje dokument i en granskningsuppsättning och visa dokumentet i dess ursprungliga version eller textversion.

   - [Skapa frågor och filter.](review-set-search.md) Du skapar sökfrågor med hjälp av olika sökvillkor (som möjligheten att söka i alla metadataegenskaper för [filer)](document-metadata-fields-in-advanced-ediscovery.md)för att ytterligare förfina och finjustera ärendedata till det som är mest relevant för ärendet. Du kan också använda filter för att snabbt tillämpa andra villkor på resultatet av en sökfråga för att ytterligare förfina resultaten. 

   - [Skapa och använda taggar](tagging-documents.md). Du kan använda taggar för dokument i en granskningsuppsättning för att identifiera vilka som svarar på ärendet (eller inte svarar på ärendet) och sedan använda de taggarna när du skapar sökfrågor för att inkludera eller exkludera de taggade dokumenten. Du kan även tagga för att avgöra vilka dokument som ska exporteras.

   - [Kommentera och göra om dokument](view-documents-in-review-set.md#annotate-view). Du kan använda anteckningsverktyget i en granskning för att kommentera dokument och ändra om innehåll i dokument som arbetsprodukt. Vi genererar en PDF-version av ett kommenterat eller omdreakterat dokument under granskning för att minska risken för att exportera den odokumenterade inbyggda versionen av dokumentet.

   - [Analysera falldata](analyzing-data-in-review-set.md). Analysfunktionerna i Advanced eDiscovery är kraftfulla. När du har kört analyser på data i granskningsuppsättningen utför vi analyser, till exempel nästan dubblettidentifiering, e-posttrådning och teman, som kan minska volymen för dokument som du måste granska. Vi genererar även en analysrapporter som sammanfattar resultatet av att köra analyser. Som tidigare förklarats körs även modellen för identifiering av [juristklienter för analys.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **Exportera och ladda ned ärendedata**. Ett sista steg efter att ha samlat in, granskat och analyserat ärendedata är att exportera dem från Advanced eDiscovery för extern granskning eller för granskning av personer utanför undersökningsteamet. Att exportera data är en process i två steg. Det första steget är [att](export-documents-from-review-set.md) exportera data från granskningsuppsättningen och kopiera dem till en annan Azure Storage plats (en som tillhandahålls av Microsoft eller en som hanteras av din organisation). Sedan använder du Azure Storage Explorer för [att ladda](download-export-jobs.md) ned data till en lokal dator. Förutom de exporterade datafilerna innehåller innehåller exportpaketet även en exportrapport, en sammanfattningsrapport och en felrapport.

## <a name="advanced-ediscovery-architecture"></a>Advanced eDiscovery arkitektur

Här är ett arkitekturdiagram som visar hela Advanced eDiscovery-arbetsflödet i en enda geomiljö och i en geomiljö, och det end-to-end-dataflöde som överensstämmer med [Electronic Discovery Reference Model.](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)

[![Modellaffisch: Advanced eDiscovery arkitektur i Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Visa som en bild](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Ladda ned som PDF-fil](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Ladda ned som Visio fil](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
