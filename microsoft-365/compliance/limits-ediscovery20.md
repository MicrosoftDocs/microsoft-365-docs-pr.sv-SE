---
title: Begränsningar för Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Läs mer om begränsningar för fall, indexeringsbegränsningar och sökbegränsningar som gäller för Advanced eDiscovery lösning i Microsoft 365.
ms.openlocfilehash: 335e40c6918fc33acc12082546b98f28c319c814
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244582"
---
# <a name="limits-in-advanced-ediscovery"></a>Begränsningar i Advanced eDiscovery

I den här artikeln beskrivs begränsningarna i Advanced eDiscovery lösningen i Microsoft 365.

## <a name="case-and-review-set-limits"></a>Begränsningar för ärende och granskning

I följande tabell visas begränsningar för ärenden och granskningsuppsättningar i Advanced eDiscovery.

| Beskrivning av gräns | Gräns |
|:-----|:-----|
|Totalt antal dokument som kan läggas till i ett ärende (för alla uppsättningar med granskning i ett ärende).  <br/> |3 miljoner <br/> |
|Total filstorlek per inläsningsuppsättning. Det omfattar inläsning av Office 365 i en granskningsuppsättning.  <br/> |300 GB <br/> |
|Den totala mängden data som lästs in i alla granskningsuppsättningar i organisationen per dag.<br/> |2 TB <br/> |
|Maximalt antal inläsningsuppsättningar per ärende.  <br/> |200 <br/> |
|Maximalt antal granskningsuppsättningar per ärende.  <br/> |20 <br/> |
|Maximalt antal tagggrupper per ärende.  <br/> |1000 <br/> |
|Maximalt antal taggar per ärende.  <br/> |1000 <br/> |
|Maximalt antal samtidiga jobb i organisationen för att lägga till innehåll i en granskningsuppsättning. De här jobben **heter Lägga till data i en granskningsuppsättning** och visas i ett fall **på** fliken Jobb.| 10 <sup>4</sup> |
|Maximalt antal samtidiga jobb för att lägga till innehåll i en granskningsuppsättning per användare. De här jobben **heter Lägga till data i en granskningsuppsättning** och visas i ett fall **på** fliken Jobb. | 3 |
|||

## <a name="hold-limits"></a>Begränsningar för att hålla kvar

I följande tabell visas begränsningar för kvarstående åtgärder som gäller för Advanced eDiscovery ärende.

| Beskrivning av gräns | Gräns |
|:-----|:-----|
|Maximalt antal postlådor för ett enskilt ärende håll. Den här gränsen omfattar totalt antal användarpostlådor och postlådorna som är kopplade Microsoft 365 grupper, Microsoft Teams och Yammer grupper. <br/> |1 000  <br/> |
|Maximalt antal webbplatser i ett enskilt ärende. Den här gränsen omfattar det totala antalet OneDrive för företag, SharePoint webbplatser och webbplatser som är kopplade till grupper Microsoft 365, Microsoft Teams och Yammer grupper.  <br/> |100  <br/> |

## <a name="indexing-limits"></a>Indexeringsbegränsningar

I följande tabell visas indexeringsbegränsningarna i Advanced eDiscovery.

| Beskrivning av gräns | Gräns |
|:-----|:-----|
|Maximalt antal tecken som extraheras från en enskild fil.  <br/> |10 miljoner<sup>1</sup> <br/> |
|Maximal storlek på en enskild fil.   <br/> |100 MB<sup>1</sup> <br/> |
|Maximalt djup för inbäddade objekt i ett dokument.  <br/> |25<sup>1</sup> <br/> |
|Maximal storlek på filer som bearbetas med optisk teckenläsning (OCR).  <br/> |24 MB<sup>1</sup> <br/> 
|Maximalt antal indexeringsjobb per organisation per dag. <br/> |10<sup>6</sup> <br/>|  
|||

## <a name="search-limits"></a>Sökbegränsningar

Begränsningarna som beskrivs i det här avsnittet är relaterade till att använda sökverktyget på fliken **Sökningar för** att samla in data för ett ärende. Mer information finns i Samla [in data för ett ärende i Advanced eDiscovery](collecting-data-for-ediscovery.md).

| Beskrivning av gräns | Gräns |
|:-----|:-----|
|Maximalt antal postlådor eller webbplatser som kan sökas i en enda sökning. |Ingen gräns|
|Maximalt antal sökningar som kan köras samtidigt. |Ingen gräns |
|Maximalt antal sökningar som en enskild användare kan starta samtidigt. |10 | 
|Maximalt antal tecken för en sökfråga (inklusive operatorer och villkor). |10 000 &nbsp; <sup>2</sup>|
|Maximalt antal tecken för en sökfråga för SharePoint och OneDrive för företag (inklusive operatorer och villkor). |10 000<br>4 000 med jokertecken &nbsp; <sup>2</sup>|
|Lägsta antal alfatecken för prefix-jokertecken. till exempel **ett _ eller \* *_* set \***.|3 |  
|Maximalt antal varianter som returneras när prefix med jokertecken används för att söka efter en exakt fras eller när du använder ett prefixtecken (jokertecken) och **operatorn NEAR** boolesk (NEAR). |10 000 &nbsp; <sup>3</sup>|
|Maximalt antal objekt per användarpostlåda som visas på förhandsgranskningssidan för sökningar. De senaste objekten visas. |100|
|Maximalt antal objekt från alla postlådor som visas på förhandsgranskningssidan för sökningar.|1 000|
|Maximalt antal postlådor som kan förhandsgranskas för sökresultat.  Om det finns fler än 1 000 postlådor som innehåller objekt som matchar sökfrågan är endast de 1 000 postlådor som har bäst resultat tillgängliga för förhandsgranskning.|1 000|
|Maximalt antal objekt från SharePoint och OneDrive för företag som visas på förhandsgranskningssidan för sökningar. De senaste objekten visas. |200|
|Maximalt antal SharePoint och OneDrive för företag webbplatser som kan förhandsgranskas för sökresultat. Om det finns fler än 200 webbplatser som innehåller objekt som matchar sökfrågan är endast de 200 vanligaste webbplatserna med flest resultat tillgängliga för förhandsgranskning.|200|
|Maximalt antal objekt per offentlig mapp-postlåda som visas på förhandsgranskningssidan för sökningar. |100|
|Maximalt antal objekt som hittas i alla postlådeobjekt i den gemensamma mappen visas på förhandsgranskningssidan för sökningar. |200|
|Maximalt antal postlådor i gemensamma mappar som kan förhandsgranskas för sökresultat. Om det finns fler än 500 postlådor i gemensamma mappar som innehåller objekt som matchar sökfrågan är endast de 500 postlådor som har bäst resultat tillgängliga för förhandsgranskning.|500|
|||

## <a name="search-times"></a>Söktider

Microsoft samlar in prestandainformation för sökningar som körs av alla organisationer. Sökfrågans komplexitet påverkar visserligen söktiden, men det är antalet postlådor som genomsöks som har störst påverkan på söktiden. Även om Microsoft inte tillhandahåller ett servicenivåavtal för söktider visar följande tabell genomsnittliga söktider för sökningar i samlingar baserat på antalet postlådor som ingår i sökningen.
  
  | Antal postlådor | Genomsnittlig söktid |
  |:-----|:-----|
  |100  <br/> |30 sekunder  <br/> |
  |1 000  <br/> |45 sekunder  <br/> |
  |10 000  <br/> |4 minuter  <br/> |
  |25 000  <br/> |10 minuter  <br/> |
  |50 000  <br/> |20 minuter  <br/> |
  |100 000  <br/> |25 minuter  <br/> |
  |||

## <a name="viewer-limits"></a>Begränsningar för visningsprogram

| Beskrivning av gräns | Gräns |
|:-----|:-----|
|Maximal storlek Excel fil som kan visas i det ursprungliga visningsprogrammet.  <br/> |4 MB  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a>Exportgränser – slutgiltig export från granskningsuppsättning

Begränsningarna som beskrivs i det här avsnittet är relaterade till att exportera dokument från en granskningsuppsättning.

| Beskrivning av gräns | Gräns |
|:-----|:-----|
|Den maximala storleken på en enskild export.|5 miljoner dokument eller 500 GB, beroende på vilket som är mindre|
|Maximalt antal samtidiga exporter per granskningsuppsättning. | 1 |
|||

## <a name="review-set-download-limits"></a>Granska ange begränsningar för nedladdning

| Beskrivning av gräns | Gräns |
|:-----|:-----|
|Total filstorlek eller maximalt antal dokument som hämtats från en granskningsuppsättning.  <br/> |3 MB eller 50 dokument <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> Alla objekt som överskrider en enskild filgräns visas som ett bearbetningsfel.
>
> <sup>2</sup> Vid sökning SharePoint och OneDrive för företag platser räknas tecknen i webbadresserna för webbplatserna som genomsöks mot den här gränsen. Det totala antalet tecken består av:<br>
> - Alla tecken i fälten Användare och Filter.
> - Alla sökbehörighetsfilter som gäller för användaren.
> - Tecknen från valfri platsegenskaper i sökningen; det här inkluderar ExchangeLocation,PublicFolderLocation,SharPointLocation,ExchangeLocationExclusion,PublicFolderLocationExclusion,SharePointLocationExclusion, OneDriveLocationExclusion.
>   Till exempel räknas alla SharePoint-webbplatser och OneDrive-konton i sökningen som sex tecken, eftersom ordet "ALL" visas för både fältet SharePointLocation och OneDriveLocation.
>
> <sup>3</sup> För frågor som inte är fraserade (ett nyckelordsvärde som inte använder dubbla citattecken) används ett särskilt prefixindex. Det innebär att ett ord förekommer i ett dokument, men inte där det förekommer i dokumentet. Om du vill göra en frasfråga (ett nyckelordsvärde med dubbla citattecken) måste vi jämföra positionen i dokumentet för orden i frasen. Det innebär att vi inte kan använda prefixindexet för frasfrågor. I det här fallet expanderar vi frågan internt med alla möjliga ord som prefixet expanderar till. till exempel kan **tid \* *_ utökas till _*"tid ELLER tidtagare ELLER tidx OR tidsruta ELLER ..."**. Gränsen på 10 000 är det maximala antalet varianter som ordet kan utökas till, inte antalet dokument som matchar frågan. Det finns ingen övre gräns för termer som inte är fraser.
>
> <sup>4</sup> Den här gränsen delas med export av innehåll i andra eDiscovery-verktyg. Det innebär att samtidiga exporter i innehållssökning och bas-eDiscovery (och att lägga till innehåll för granskningsuppsättningar i Advanced eDiscovery) tillämpas mot den här gränsen.
>
> <sup>5</sup> Den här gränsen gäller för att ladda ned valda dokument från en granskningsuppsättning. Den gäller inte för export av dokument från en granskningsuppsättning. Mer information om hur du laddar ned och exporterar dokument finns i [Exportera ärendedata i Advanced eDiscovery](exporting-data-ediscover20.md).
>
> <sup>6</sup> Indexeringsbegränsningar per organisation per dag. Som en lösning kan du välja flera användare på fliken **Datakällor** för ett ärende och sedan klicka på Uppdatera **index** för att undvika att skapa ett separat indexjobb för varje användare. 
