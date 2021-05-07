---
title: Hantera jobb i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Advanced eDiscovery hjälper dig att spåra status för långvariga processer relaterade till att utföra olika Advanced eDiscovery uppgifter.
ms.openlocfilehash: 27ac98d1f98e85800c8ca3dfc91cc5e0803ae2e8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "52162604"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Hantera jobb i Advanced eDiscovery

Här är en lista över jobb (som vanligtvis är långvariga processer)  som spåras på fliken Jobb för ett ärende i Advanced eDiscovery. De här jobben utlöses av användaråtgärder när de använder och hanterar ärenden.

| Jobbtyp           | Beskrivning     |
| :----------------- | :----------     |
|Lägga till data i en granskningsuppsättning | En användare lägger till en samling i en granskningsuppsättning. Det här jobbet består av två underjobb: </br>• **Exportera** – en lista med objekt i samlingen skapas. </br>• På så sätt **&-indexering** – De objekt i samlingen som matchar sökfrågan kopieras till en Azure Storage-plats (i en process som kallas *pågestering)* och sedan indexeras de objekten på Azure Storage-platsen om. Det här nya indexet används när du frågar och analyserar objekt i datauppsättningen. </br></br>Mer information finns i Lägga [till sökresultat i en granskningsuppsättning.](add-data-to-review-set.md) |
|Lägga till data i en annan granskningsuppsättning | En användare lägger till dokument från en granskningsuppsättning till en annan granskningsuppsättning i samma ärende. Mer information finns i Lägga [till data i en granskningsuppsättning från en annan granskningsuppsättning](add-data-to-review-set-from-another-review-set.md).|
|Lägga till data som Microsoft 365 en granskning | En användare laddar upp icke-Microsoft 365 data till en granskningsuppsättning. Data indexeras också under den här processen. Till exempel laddas filer från en lokal filserver eller en klientdator upp till en granskningsuppsättning. Mer information finns i Läsa [in icke-Microsoft 365 data i en granskningsuppsättning](load-non-office-365-data-into-a-review-set.md).| 
|Lägga till åtgärdade data i en granskningsuppsättning | Data med bearbetningsfel åtgärdas och läses in i en granskningsuppsättning. Mer information finns i:</br>• [Åtgärdsfel vid bearbetning av data](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Åtgärd av enstaka objektfel](single-item-error-remediation.md)| 
|Jämföra inläsningsuppsättningar | En användare tittar på skillnaderna mellan olika inläsningsuppsättningar i en granskningsuppsättning. En inläsningsuppsättning är en instans av att lägga till data i en granskningsuppsättning. Om du till exempel lägger till resultatet av två olika sökningar i samma granskningsuppsättning, representerar var och en belastningsuppsättning. |
|Konversationsämne|När en användare lägger till resultatet av en sökning i en uppsättning konversationsgranskning återskapas snabbmeddelandekonversationer (även kallade trådade konversationer) i tjänster som Microsoft Teams återskapas i en PDF-fil. Det här jobbet utlöses också när en användare klickar på Åtgärd > **skapa konversations-PDF:er i** en granskningsuppsättning. Mer information finns i Granska [konversationer i Advanced eDiscovery](conversation-review-sets.md).
|Konvertera omaktiverade dokument till PDF|När en användare har kommenterat ett dokument i en granskningsuppsättning och omat en del av det kan de välja att konvertera det omdelade dokumentet till en PDF-fil. Det säkerställer att den omdelade delen inte visas om dokumentet exporteras för presentation. Mer information finns i [Visa dokument i en granskningsuppsättning](annotating-and-redacting-documents.md). |
|Uppskatta sökresultat | När en användare skapar och kör eller kör ett utkast på nytt söker sökverktyget igenom indexet efter objekt som matchar sökfrågan och förbereder en uppskattning som innehåller antalet och den totala storleken för alla objekt vid sökningen och antalet datakällor som genomsöks.  Mer information finns i Samla [in data för ett ärende.](collecting-data-for-ediscovery.md) | 
|Förbereda data för export | En användare exporterar dokument från en granskningsuppsättning. När exporten är klar kan de ladda ned exporterade data till en lokal dator. Mer information finns i [Exportera ärendedata.](exporting-data-ediscover20.md) | 
|Förbereda för fellösning |När en användare väljer en fil och skapar en ny felreparation i vyn Fel på fliken Bearbetning för ett ärende är det första steget i processen att ladda upp filen med bearbetningsfelet till en Azure Storage-plats i Microsoft-molnet.  Det här jobbet följer upp förloppet för uppladdningsprocessen. Mer information om arbetsflödet för felreparation finns [i Felreparation när du bearbetar data.](error-remediation-when-processing-data-in-advanced-ediscovery.md) | 
|Förbereda förhandsgranskning av sökning | När en användare skapar och kör en ny utkastsamling (eller kör om en befintlig utkastsamling) förbereder sökverktyget en exempeldelmängd objekt (som matchar sökfrågan) som kan förhandsgranskas. Om du förhandsgranskar sökresultaten blir det bättre att avgöra hur effektiv sökningen är.  Mer information finns i Samla [in data för ett ärende.](collecting-data-for-ediscovery.md#view-search-results-and-statistics) | 
|Indexera om data | När du lägger till en vårdnadshavare i ett ärende indexeras alla delvis indexerade objekt i den tonens valda datakällor om av en process som kallas *Avancerad indexering.* Det här jobbet utlöses också när  du klickar på Uppdatera **index** på fliken Bearbetning för ett ärende, och när du uppdaterar indexet för en viss vårdnadshavare på den utfällande sidan med egenskapsspecifika dokument. Mer information finns i [Avancerad indexering av systemdata.](indexing-custodian-data.md)
|Köra analyser | En användare analyserar data i en granskningsuppsättning genom att köra Advanced eDiscovery analysverktyg, till exempel nästan dubblettidentifiering, analys av e-posttrådar och teman. Mer information finns i [Analysera data i en granskningsuppsättning](analyzing-data-in-review-set.md). | 
|Tagga dokument | Det här jobbet utlöses när en användare klickar på **Starta taggningsjobb** i panelen **Taggning** när de granskar dokument i en uppsättning med granskning. En användare kan starta det här jobbet efter att ha taggt dokument i en granskningsuppsättning och sedan massinställt dem på dokumentpanelen i Visa dokument. Mer information finns i [Tagga dokument i en granskningsuppsättning](tagging-documents.md). | 
|||

## <a name="job-status"></a>Jobbstatus

I följande tabell beskrivs de olika statuslägena för jobb.

| Status           | Beskrivning     |
| :----------------- | :----------     |
| Skickat | Ett nytt jobb har skapats.  Datum och tid då jobbet skickades visas i kolumnen **Skapat** på **fliken Jobb.** |
| Inskicking misslyckades | Jobbinskickingen misslyckades.  Du bör försöka köra åtgärden som utlöste jobbet igen. |
| Pågående | Jobbet pågår. Du kan övervaka förloppet för jobbet på **fliken** Jobb. |
| Lyckades | Jobbet har slutförts. Datum och tid då jobbet slutfördes visas i **kolumnen Slutförda** på **fliken** Jobb. |
| Delvis lyckades | Jobbet lyckades. Den här statusen returneras vanligtvis om jobbet inte hittade några delvis indexerade data (kallas även *oindexerade data)* i vissa av de icke indexerade datakällorna.  |
| Misslyckades | Jobbet misslyckades.  Du bör försöka köra åtgärden som utlöste jobbet igen. Om jobbet misslyckas en andra gång rekommenderar vi att du kontaktar Microsoft Support och lämnar supportinformation från jobbet. |
|||
