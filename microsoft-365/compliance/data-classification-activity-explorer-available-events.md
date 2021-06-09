---
title: Etikettering av åtgärder som rapporterats i Utforskaren
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: en lista med etiketter för aktiviteter som är tillgängliga i aktivitetsutforskaren.
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532260"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Märka aktiviteter som är tillgängliga i Aktivitetsutforskaren

## <a name="sensitivity-label-applied"></a>Känslighetsetikett används

Den här händelsen genereras varje gång ett dokument utan etikett sätts i etiketter eller ett e-postmeddelande skickas med en känslighetsetikett. 

- Den fångas när du sparar i Office program och webbprogram. 
- Den fångas när den förekommer i Azure Information Protection-tillägg. 
- Åtgärder för uppgradering och nedgradering av etiketter kan också övervakas via *fältet och filtret för händelsetypen* Etikett.   


|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------|
| Word, Excel, PowerPoint|ja |
|Outlook| ja |från Win 32 |
|SharePoint online, OneDrive|ja | |
|Exchange        |ja         | |
|Enhetlig klient och enhetlig AIP-skanner i Azure Information Protection (AIP) |ja |Åtgärden för ny *etikett i* AIP mappas till etiketten som *används i* aktivitetsutforskaren   |
|Microsoft information protection (MIP) SDK         |ja|Åtgärden för ny *etikett i* AIP mappas till etiketten som *används i* aktivitetsutforskaren|
|RMS (Rights Management Service)         |ej tillämpligt         | |
|Power BI dator och webb        | nej| tillgängliga i Microsoft 365 granskningsloggar         |
|Microsoft Cloud App Security (MCAS)         |nej|         |

## <a name="sensitivity-label-changed"></a>Känslighetsetikett har ändrats

Den här händelsen genereras varje gång en känslighetsetikett uppdateras i dokumentet eller e-postmeddelandet.

- För källorna AIP Unified Client, Unified Scanner och  MIP SDK har AIP-uppgraderingsetiketten och nedgraderingsetikettsmapparna till aktivitetsutforskaren *ändrats* 

- Den fångas när du sparar i Office program och webbprogram. 
- Händelsen fångas när det inträffar i Azure Information Protection Unified Client-tillägg och tvingande skannrar
- Åtgärder för uppgradering och nedgradering av etiketter kan också övervakas via *fältet och filtret för händelsetypen* Etikett. *Justeringstexten* förs också in utom för justering SharePoint Online och OneDrive.
- Känslighetsetiketter som utförs i Office inbyggda appar på Outlook samlar in den senaste åtgärden som skapades innan åtgärder för att spara/skicka filer/e-post. Om användaren till exempel ändrar etikett i ett e-postmeddelande flera gånger innan det skickas fångas den sista etiketten på e-postmeddelandet när det skickas i granskningsloggen och rapporteras sedan i aktivitetsutforskaren. 


|Source  |Rapporterad i Aktivitetsutforskaren|Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |ja         |Win 32|
|SharePoint Online, OneDrive         |ja         |
|Exchange         |ja         |
|Enhetlig AIP-klient         |ja         |
|AIP unified scanner         |ja         |
|MIP SDK         |ja         |
|RMS-tjänst         |ej tillämpligt         |
|Power BI dator och webb         |nej         |tillgängliga i Microsoft 365 granskningsloggar |
|MCAS     |nej         |         |

## <a name="sensitivity-label-removed"></a>Känslighetsetikett borttagen

Den här händelsen genereras varje gång en känslighetsetikett tas bort från en fil eller ett dokument.

- Händelsen fångas när du sparar i Office program och webbprogram.
- Den fångas när den förekommer i Azure Information Protection-tillägg. 
- Känslighetsetiketter, med Office inbyggd MIP-etikett, på Outlook samlar in den senaste händelsen med etiketter som skapades innan åtgärderna spara/skicka e-post.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |ja         |Win 32|
|SharePoint Online, OneDrive         |ja         |
|Exchange         |ja         |
|Enhetlig AIP-klient         |ja         |Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren|
|AIP unified scanner         |ja         |Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren |
|MIP SDK         |ja         |Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren |
|RMS-tjänst         |ej tillämpligt         |
|Power BI dator och webb         |nej         |tillgängliga i Microsoft 365 granskningsloggar |
|MCAS     |nej         |         |
 

## <a name="sensitivity-label-file-read"></a>Känslighetsetikettsfil läst

Den här händelsen genereras varje gång ett känslighetsetiketterat eller skyddat dokument öppnas.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |nej         |
|SharePoint Online, OneDrive         |nej         |
|Exchange         |nej         |
|Enhetlig AIP-klient         |ja         |*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren|
|AIP unified scanner         |ja         |*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren|
|MIP SDK         |ja         |*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren|
|RMS-tjänst         |ja         |*Åtkomståtgärden* är mappad till *filläsningsåtgärden* i aktivitetsutforskaren |
|Power BI dator och webb         |nej         |tillgängliga i Microsoft 365 granskningsloggar |
|MCAS     |nej         |         |


## <a name="files-discovered"></a>Upptäckta filer

Händelsen genereras varje gång filer upptäcks när AIP-skanner används för att skanna känsliga data på olika platser och hittar filer.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ej tillämpligt         |
|Outlook         |ej tillämpligt         |
|SharePoint Online, OneDrive         |ej tillämpligt         |
|Exchange         |ej tillämpligt         |
|Enhetlig AIP-klient         |ej tillämpligt       |
|AIP unified scanner         |ja         |Åtgärden för *AIP-identifiering* mappas till de filer som *identifierats i* aktivitetsutforskaren|
|MIP SDK         |ja         |Åtgärden för att *identifiera AIP* mappas till den fil *som identifierats* i aktivitetsutforskaren|
|RMS-tjänst         |ej tillämpligt         |
|Power BI dator och webb         |ej tillämpligt         |
|MCAS     |ej tillämpligt         |         |


## <a name="sensitivity-label-file-renamed"></a>Känslighetsetikettsfil har bytt namn

Den här händelsen genereras varje gång ett dokument med en känslighetsetikett byter namn. 

|Source  | Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |ej tillämpligt         |
|SharePoint Online, OneDrive         |nej        |
|Exchange         |ej tillämpligt         |
|Enhetlig AIP-klient         |nej         |
|AIP unified scanner         |nej         |
|MIP SDK         |nej         |
|RMS-tjänst         |nej      |
|Power BI dator och webb         |nej         |
|MCAS     |nej         |         |


## <a name="file-removed"></a>Filen har tagits bort

Händelsen genereras varje gång AIP-skannern upptäcker att en tidigare skannad fil har tagits bort.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ej tillämpligt         |
|Outlook         |ej tillämpligt         |
|SharePoint Online, OneDrive         |ej tillämpligt           |
|Exchange         |ej tillämpligt         |
|Enhetlig AIP-klient         |ej tillämpligt            |
|AIP unified scanner         |ja         |
|MIP SDK         |ej tillämpligt            |
|RMS-tjänst         |ej tillämpligt         |
|Power BI dator och webb         |ej tillämpligt  |
|MCAS     |ej tillämpligt        |         |

### <a name="protection-applied"></a>Skydd tillämpat

Den här händelsen genereras första gången skydd läggs till manuellt för ett objekt som inte har en etikett.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |nej         |
|Outlook         |nej         |
|SharePoint Online, OneDrive         |ej tillämpligt           |
|Exchange         |nej       |
|Enhetlig AIP-klient         |ja            |
|AIP unified scanner         |ej tillämpligt         |
|MIP SDK         |ja            |
|RMS-tjänst         |ej tillämpligt         |
|Power BI dator och webb         |ej tillämpligt            |
|MCAS     |ej tillämpligt        |         |

## <a name="protection-changed"></a>Skydd har ändrats

Den här händelsen genereras varje gång skyddet för ett dokument utan etikett ändras manuellt.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Word, Excel, PowerPoint         |nej         |
|Outlook         |nej         |
|SharePoint Online, OneDrive         |ej tillämpligt           |
|Exchange         |nej       |
|Enhetlig AIP-klient         |ja            |
|AIP unified scanner         |ej tillämpligt         |
|MIP SDK         |ja            |
|RMS-tjänst         |ej tillämpligt         |
|Power BI dator och webb         |ej tillämpligt            |
|MCAS     |ej tillämpligt        |

## <a name="protection-removed"></a>Skydd har tagits bort

Den här händelsen genereras varje gång skyddet för ett dokument utan etikett ändras manuellt.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Word, Excel, PowerPoint         |nej         |
|Outlook         |nej         |
|SharePoint Online, OneDrive         |ej tillämpligt           |
|Exchange         |nej       |
|Enhetlig AIP-klient         |ja            |
|AIP unified scanner         |ej tillämpligt         |
|MIP SDK         |ja            |
|RMS-tjänst         |ej tillämpligt         |
|Power BI dator och webb         |ej tillämpligt            |
|MCAS     |ej tillämpligt        |

## <a name="dlp-policy-matched"></a>Matchad DLP-princip

Den här händelsen genereras varje gång en DLP-princip matchas i ett dokument eller e-postmeddelande.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Exchange         |ja       |
|SharePoint Online|ja          |
|OneDrive |ja|
|Teams |ja   |
|Windows 10-enheter         |ja |
|MAC         |nej     |
|lokalt         |nej|
|MCAS     |nej        | 

Händelserna för Windows 10 enheter (Endpoint DLP) är:

- fil borttagna
- fil skapad
- fil kopierad till Urklipp
- fil ändrad
- fil som lästs
- fil utskriven
- filen har bytt namn
- fil kopierad till nätverksresurs
- fil som används av ej tillkomlig app


## <a name="retention-label-applied"></a>Bevarandeetikett tillämpad 

Den här händelsen genereras varje gång ett dokument utan etiketter etiketteras eller ett e-postmeddelande skickas med en bevarandeetikett.

- Den sparas när du sparar ett dokument och när den skickas till ett e-postmeddelande.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Exchange         |nej       |
|SharePoint Online|ja          |
|OneDrive |ja|

## <a name="retention-label-changed"></a>Bevarandeetikett har ändrats

Händelsen genereras varje gång en etikett uppdateras i ett dokument eller e-postmeddelande.

- Den sparas när du sparar ett dokument och när den skickas till ett e-postmeddelande.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Exchange         |nej       |
|SharePoint Online|ja          |
|OneDrive |ja|
 
## <a name="retention-label-removed"></a>Bevarandeetikett borttagen

Händelsen genereras varje gång en etikett tas bort från en fil eller ett dokument.

- Den sparas när du sparar ett dokument och när den skickas till ett e-postmeddelande.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Exchange         |nej       |
|SharePoint Online|ja          |
|OneDrive |ja|


## <a name="known-issues"></a>Kända problem
  
- När den rekommenderade etikettypen visas för en slutanvändare så fångas den inte upp. Men om användaren väljer att använda den rekommenderade etiketten visas etiketten under fältet Hur *används* som *Rekommenderas*  

- Justeringstexten är för närvarande inte tillgänglig vid känslighetsetiketts nedgradering från Sharepoint och OneDrive.  

- Typer av känslig information är för närvarande inte tillgängliga för aktiviteter med automatisk etikett från Word, Excel, PowerPoint och Outlook samt SharePoint Online och OneDrive.
