---
title: Lär dig om instrumentpanelen för dataförlustskyddsvarningar
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Läs mer om varningar om skydd mot dataförlust och instrumentpanelen för aviseringar.
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760782"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>Lär dig om instrumentpanelen för dataförlustskyddsvarningar

När villkoren i en DLP-princip (Data Loss Prevention) matchas av de åtgärder som en användare vidtar för ett känsligt objekt kan principen generera en avisering. Det kan leda till en stor mängd aviseringar. DLP-aviseringar samlas in på instrumentpanelen för aviseringar. På instrumentpanelen för aviseringar finns en enda plats att gå till för att utföra en detaljerad undersökning av all information om principmatchning.  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>Arbetsbelastningar

Instrumentpanelen [för DLP-aviseringshantering](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) [i Microsoft 365,](https://compliance.microsoft.com/)visar aviseringar för DLP-principer för dessa arbetsbelastningar:

- Exchange
- SharePoint
- OneDrive
- Teams
- Windows 10-enheter 

> [!TIP]
> Kunder som använder Slutpunkt DLP som är kvalificerade för [Teams DLP](dlp-microsoft-teams.md) ser deras DLP-principaviseringar och Teams DLP-principaviseringar på instrumentpanelen för hantering av DLP-aviseringar. [](endpoint-dlp-learn-about.md)

## <a name="single-alert-and-aggregate-alert"></a>Enskild avisering och mängdavisering

Det finns två typer av aviseringar som kan konfigureras i DLP-principer.

Varningar för enstaka händelser används vanligtvis i principer som övervakar vid mycket känsliga händelser som inträffar i en låg volym, t.ex. ett enskilt **e-postmeddelande** med 10 eller fler kundkortsnummer som skickas utanför organisationen.

**Mängdhändelseaviseringar** används vanligtvis i principer som övervakar för händelser som inträffar i en högre volym under en tidsperiod. Till exempel kan en samlad avisering utlösas när tio enskilda e-postmeddelanden med ett kundkortsnummer skickas utanför organisationen under 48 timmar.

## <a name="types-of-events"></a>Typer av händelser

Här är några av de händelser som associeras med en avisering. I användargränssnittet kan du välja en viss händelse om du vill visa dess information. 

### <a name="event-details"></a>Händelseinformation

|Egenskapsnamn  |Beskrivning  |Händelsetyper  |
|---------|---------|---------|
|ID |unikt ID som är kopplat till händelsen |alla händelser |
|Plats |arbetsbelastning där händelsen identifierades|alla händelser |
|tid för aktivitet     |tid för den användaraktivitet som matchade villkoren för DLP-principen |

### <a name="impacted-entities"></a>Berörda enheter

|Egenskapsnamn |Beskrivning| Händelsetyper|
|---------|---------|---------|
|användare | användare som har gjort den åtgärd som orsakade principmatchning | alla händelser|
|hostname | värdnamnet på datorn där DLP-principmatchning inträffade | enhetshändelser|
|IP-adress | IP-adress för datorn där DLP-principmatchning inträffade | enhetshändelser|
|sha1 |SHA-1-hash för filen | enhetshändelser|
|sha256 | SHA-256-hash för filen | enhetshändelser|
|MDATP enhets-ID | slutpunktsenhet MDATP ID|
|filstorlek | storlek på filen| SharePoint, OneDrive och enhetshändelser|
|filsökväg | den absoluta sökvägen till det objekt som ingår i DLP-principmatchning | SharePoint, OneDrive och enheter|
|e-postmottagare |Om ett e-postmeddelande var det känsliga objektet som matchade DLP-principen innehåller det här fältet mottagarna för e-postmeddelandet| Exchange händelser|
|e-postämne |e-postmeddelandets ämne som matchade DLP-principen |Exchange händelser|
|e-postbilagor | Namnen på de bifogade filerna i e-postmeddelandet som matchade DLP-principen| Exchange händelser|
|webbplatsägare |namnet på webbplatsägaren| SharePoint och OneDrive händelser|
|webbplats-URL |full av URL:en för den SharePoint eller OneDrive där DLP-principmatchning inträffade |SharePoint och OneDrive händelser|
|fil skapad |tidpunkten då filen skapades som matchade DLP-principen |SharePoint och OneDrive händelser|
|fil som senast ändrades | den senaste gången som filen som matchade DLP-principen ändrades | SharePoint och OneDrive händelser|
|filstorlek | Storlek på filen som matchade DLP-principen |SharePoint och OneDrive händelser|
|filägare |ägare av filen som matchade DLP-principen |SharePoint och OneDrive händelser|  

### <a name="policy-details"></a>Principinformation

|Egenskapsnamn |Beskrivning |Händelsetyper |
|---------|---------|---------|
|Matchad DLP-princip |namnet på den matchande DLP-principen |alla händelser|
|regelmatchad |Namnet på den matchade DLP-principregeln |alla händelser|
|DEN typ av känslig information (SIT) som upptäckts|SITs som identifierades som en del av DLP-principmatchning |alla händelser|
|vidtagna åtgärder |Åtgärder som har vidtagits som orsakade matchningen av DLP-principen| alla händelser|
|bryta mot åtgärd | åtgärd på slutpunktsenheten som höjer DLP-aviseringen| enhetshändelser | 
|användarprincip överrode |har användaren åsidosättt principen via ett principtips | alla händelser|
|använda åsidosättning av justering |Texten för den orsak som anges av användaren för åsidosättningen | alla händelser|   

## <a name="see-also"></a>Se även

- [Komma igång med instrumentpanelen för dataförlustskyddsvarningar](dlp-alerts-dashboard-get-started.md)
- [Var du kan börja med dataförlustskydd](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)