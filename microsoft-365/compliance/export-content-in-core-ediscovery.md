---
title: Exportera och ladda ned innehåll från en bas-eDiscovery-fråga
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Här beskrivs hur du exporterar och laddar ned innehåll från en bas-e-dataidentifieringsfall i Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310862"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Exportera innehåll från en bas-e-dataidentifieringsfall

När en sökning som är kopplad till ett Bas-eDiscovery-ärende har körts kan du exportera sökresultatet. När du exporterar sökresultat hämtas postlådeobjekt i PST-filer eller som enskilda meddelanden. När du exporterar innehåll SharePoint och OneDrive för företag exporteras kopior av ursprungliga Office och andra dokument. En Results.csv fil som innehåller information om alla objekt som exporteras och en manifestfil (i XML-format) som innehåller information om varje sökresultat exporteras också.
  
## <a name="export-search-results"></a>Exportera sökresultat

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och logga in med inloggningsuppgifterna för användarkontot som har tilldelats lämpliga eDiscovery-behörigheter.

2. I det vänstra navigeringsfönstret i Microsoft 365 kompatibilitetscenter klickar du på Visa alla **och** sedan på **eDiscovery > Core**.

3. På sidan **Bas-eDiscovery** klickar du på namnet på det ärende som du vill skapa ett sådant ärende i.

4. På **startsidan för** ärendet klickar du på **fliken** Sökningar.

5. På menyn **Åtgärder** längst ned på den utfällade sidan klickar du på **Exportera resultat.**

   ![Alternativet Exportera resultat på menyn Åtgärder](../media/ActionMenuExportResults.png)

   Arbetsflödet för att exportera resultatet av en sökning som är kopplad till ett basfall för eDiscovery är detsamma som att exportera sökresultatet för en sökning på sidan **Innehållssökning.** Stegvisa instruktioner finns i Exportera [sökresultat för innehåll.](export-search-results.md)

   > [!NOTE]
   > När du exporterar sökresultat kan du välja att aktivera avduplicering så att bara en kopia av ett e-postmeddelande exporteras, även om flera förekomster av samma meddelande kan ha hittats i postlådorna som har sökts. Mer information om avduplicering och hur dubbletter identifieras finns i [Avduplicering i eDiscovery-sökresultat.](de-duplication-in-ediscovery-search-results.md)

   När du startar exporten förbereds sökresultaten för nedladdning, vilket innebär att de överförs till en Microsoft-tillhandahållen Azure Storage plats i Microsoft-molnet.
  
6. Klicka på **fliken** Exporter för att visa listan med exportjobb.
  
   ![Exportera jobb på fliken Exportera i Bas-eDiscovery-fall](../media/CoreeDiscoveryExport.png)

   Du kanske måste klicka på **Uppdatera** för att uppdatera listan med exportjobb så att den visar det exportjobb du har skapat. Exportjobb har samma namn som motsvarande sökning **_Export** lagts till i söknamnet.

7. Klicka på exportjobbet du skapade för att visa statusinformation på den utfällade sidan. Den här informationen omfattar den procentandel av artiklar som har överförts till Azure Storage plats.

8. När alla objekt har överförts klickar du på **Ladda ned resultat** för att ladda ned sökresultatet till den lokala datorn. Mer information om hur du laddar ned sökresultat finns i Steg 2 i [Exportera sökresultat för innehåll](export-search-results.md#step-2-download-the-search-results)

### <a name="more-information-about-exporting-searches-from-a-case"></a>Mer information om hur du exporterar sökningar från ett ärende

- Mer information om exportfiler som ingår när du exporterar sökresultat finns i [Exportera en rapport för innehållssökning.](export-a-content-search-report.md#whats-included-in-the-report)

- Om du startar om exporten påverkas inte sökresultaten som hämtas om du ändrar frågorna för de sökningar som utgör exportjobbet. När du startar om en export körs samma kombinerade sökjobb som startades när exportjobbet skapades igen.

- Om du startar om en export kommer sökresultaten som kopieras till den Azure Storage plats att skriva över de tidigare resultaten. Tidigare resultat som kopierades går inte att hämta.
