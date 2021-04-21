---
title: Märkningsåtgärder som rapporterats i Aktivitetsutforskaren
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
description: lista med etiketter på åtgärder som är tillgängliga i aktivitetsutforskaren.
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902956"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Märka aktiviteter som är tillgängliga i Aktivitetsutforskaren

## <a name="sensitivity-label-applied"></a>Känslighetsetikett används

Den här händelsen genereras varje gång ett dokument utan etikett sätts på etiketten eller om ett e-postmeddelande skickas med en etikett. 

- Den fångas när du sparar i Office-program och webbprogram. 
- Den fångas när den förekommer i Azure Information Protection-tillägg. 
- Åtgärder för uppgradering och nedgradering av etiketter kan också övervakas via *fältet och filtret för händelsetypen* Etikett.   


|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------|
| Word, Excel, PowerPoint|Ja |
|Outlook| Ja |från Win 32 |
|SharePoint online, OneDrive|Ja | |
|Exchange        |Ja         | |
|Enhetlig klient och enhetlig AIP-skanner i Azure Information Protection (AIP) |Ja |Åtgärden för ny *etikett i* AIP mappas till etiketten som *används i* aktivitetsutforskaren   |
|Microsoft information protection (MIP) SDK         |Ja|Åtgärden för ny *etikett i* AIP mappas till etiketten som *används i* aktivitetsutforskaren|
|RMS (Rights Management Service)         |inte tillämpligt         | |
|Power BI för skrivbordet och på webben        | Nej| tillgängliga i Microsoft 365 granskningsloggar         |
|Microsoft Cloud App Security (MCAS)         |Nej|         |

## <a name="sensitivity-label-changed"></a>Känslighetsetikett har ändrats

Händelsen genereras varje gång en etikett uppdateras i dokumentet eller e-postmeddelandet.

- För källorna AIP Unified Client, Unified Scanner och  MIP SDK har AIP-uppgraderingsetiketten och nedgraderingsetikettsmapparna till aktivitetsutforskaren *ändrats* 

- Den fångas när du sparar i Office-program och webbprogram. 
- Händelsen fångas när det inträffar i Azure Information Protection Unified Client-tillägg och tvingande skannrar
- Åtgärder för uppgradering och nedgradering av etiketter kan också övervakas via *fältet och filtret för händelsetypen* Etikett. *Justeringstexten* förs också in utom för SharePoint Online och OneDrive.
- Känslighetsetiketter som utförs i Inbyggda Office-appar i Outlook samlar in den senaste åtgärd som skapades innan åtgärder för att spara och skicka filer via e-post. Om användaren till exempel ändrar etikett i ett e-postmeddelande flera gånger innan det skickas fångas den sista etiketten på e-postmeddelandet när det skickas i granskningsloggen och rapporteras sedan i aktivitetsutforskaren. 


|Source  |Rapporterad i Aktivitetsutforskaren|Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |Ja         |
|Outlook         |Ja         |Win 32|
|SharePoint Online, OneDrive         |Ja         |
|Exchange         |Ja         |
|Enhetlig AIP-klient         |Ja         |
|AIP unified scanner         |Ja         |
|MIP SDK         |Ja         |
|RMS-tjänst         |inte tillämpligt         |
|Power BI för skrivbordet och på webben         |Nej         |tillgängliga i Microsoft 365 granskningsloggar |
|MCAS     |Nej         |         |

## <a name="sensitivity-label-removed"></a>Känslighetsetikett borttagen

Händelsen genereras varje gång en etikett tas bort från en fil eller ett dokument.

- Händelsen fångas när du sparar i Office-program och webbprogram.
- Den fångas när den förekommer i Azure Information Protection-tillägg. 
- Känslighetsetiketter, med Den inbyggda Office-MIP-etiketten, i Outlook samlar in den senaste etiketthändelsen som skapades innan åtgärder för att spara och skicka filer/e-post.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |Ja         |
|Outlook         |Ja         |Win 32|
|SharePoint Online, OneDrive         |Ja         |
|Exchange         |Ja         |
|Enhetlig AIP-klient         |Ja         |Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren|
|AIP unified scanner         |Ja         |Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren |
|MIP SDK         |Ja         |Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren |
|RMS-tjänst         |inte tillämpligt         |
|Power BI för skrivbordet och på webben         |Nej         |tillgängliga i Microsoft 365 granskningsloggar |
|MCAS     |Nej         |         |
 

## <a name="sensitivity-label-file-read"></a>Känslighetsetikettsfil läst

Händelsen genereras varje gång ett etiketterat eller skyddat dokument öppnas.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |Ja         |
|Outlook         |Nej         |
|SharePoint Online, OneDrive         |Nej         |
|Exchange         |Nej         |
|Enhetlig AIP-klient         |Ja         |*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren|
|AIP unified scanner         |Ja         |*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren|
|MIP SDK         |Ja         |*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren|
|RMS-tjänst         |Ja         |*Åtkomståtgärden* är mappad till *filläsningsåtgärden* i aktivitetsutforskaren |
|Power BI för skrivbordet och på webben         |Nej         |tillgängliga i Microsoft 365 granskningsloggar |
|MCAS     |Nej         |         |


## <a name="sensitivity-label-files-discovered"></a>Känslighetsetikettsfiler upptäcktes

Händelsen genereras varje gång filer upptäcks när AIP-skanner används för att skanna känsliga data på olika platser och hittar filer.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |inte tillämpligt         |
|Outlook         |inte tillämpligt         |
|SharePoint Online, OneDrive         |inte tillämpligt         |
|Exchange         |inte tillämpligt         |
|Enhetlig AIP-klient         |inte tillämpligt       |
|AIP unified scanner         |Ja         |Åtgärden för *AIP-identifiering* mappas till de filer som *identifierats i* aktivitetsutforskaren|
|MIP SDK         |Ja         |Åtgärden för att *identifiera AIP* mappas till den fil *som identifierats* i aktivitetsutforskaren|
|RMS-tjänst         |inte tillämpligt         |
|Power BI för skrivbordet och på webben         |inte tillämpligt         |
|MCAS     |inte tillämpligt         |         |


## <a name="sensitivity-label-file-renamed"></a>Känslighetsetikettsfil har bytt namn

Den här händelsen genereras varje gång ett dokument med en känslighetsetikett byter namn. 

|Source  | Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |Ja         |
|Outlook         |inte tillämpligt         |
|SharePoint Online, OneDrive         |Nej        |
|Exchange         |inte tillämpligt         |
|Enhetlig AIP-klient         |Nej         |
|AIP unified scanner         |Nej         |
|MIP SDK         |Nej         |
|RMS-tjänst         |Nej      |
|Power BI för skrivbordet och på webben         |Nej         |
|MCAS     |Nej         |         |


## <a name="sensitivity-label-file-removed"></a>Känslighetsetikettsfil har tagits bort

Händelsen genereras varje gång AIP-skannern upptäcker att en tidigare skannad fil har tagits bort.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |inte tillämpligt         |
|Outlook         |inte tillämpligt         |
|SharePoint Online, OneDrive         |inte tillämpligt           |
|Exchange         |inte tillämpligt         |
|Enhetlig AIP-klient         |inte tillämpligt            |
|AIP unified scanner         |Ja         |
|MIP SDK         |inte tillämpligt            |
|RMS-tjänst         |inte tillämpligt         |
|Power BI för skrivbordet och på webben         |inte tillämpligt  |
|MCAS     |inte tillämpligt        |         |

### <a name="sensitivity-label-protection-applied"></a>Skydd mot känslighetsetikett används

Den här händelsen genereras första gången skydd läggs till manuellt för ett objekt som inte har en etikett.

|Source  |Rapporterad i Aktivitetsutforskaren | Obs!  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |Nej         |
|Outlook         |Nej         |
|SharePoint Online, OneDrive         |inte tillämpligt           |
|Exchange         |Nej       |
|Enhetlig AIP-klient         |Ja            |
|AIP unified scanner         |inte tillämpligt         |
|MIP SDK         |Ja            |
|RMS-tjänst         |inte tillämpligt         |
|Power BI för skrivbordet och på webben         |inte tillämpligt            |
|MCAS     |inte tillämpligt        |         |

## <a name="sensitivity-label-protection-changed"></a>Känslighetsetikettsskydd har ändrats

Den här händelsen genereras varje gång skyddet för ett dokument utan etikett ändras manuellt.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Word, Excel, PowerPoint         |Nej         |
|Outlook         |Nej         |
|SharePoint Online, OneDrive         |inte tillämpligt           |
|Exchange         |Nej       |
|Enhetlig AIP-klient         |Ja            |
|AIP unified scanner         |inte tillämpligt         |
|MIP SDK         |Ja            |
|RMS-tjänst         |inte tillämpligt         |
|Power BI för skrivbordet och på webben         |inte tillämpligt            |
|MCAS     |inte tillämpligt        |

## <a name="sensitivity-label-protection-removed"></a>Skydd mot känslighetsetikett har tagits bort

Den här händelsen genereras varje gång skyddet för ett dokument utan etikett ändras manuellt.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Word, Excel, PowerPoint         |Nej         |
|Outlook         |Nej         |
|SharePoint Online, OneDrive         |inte tillämpligt           |
|Exchange         |Nej       |
|Enhetlig AIP-klient         |Ja            |
|AIP unified scanner         |inte tillämpligt         |
|MIP SDK         |Ja            |
|RMS-tjänst         |inte tillämpligt         |
|Power BI för skrivbordet och på webben         |inte tillämpligt            |
|MCAS     |inte tillämpligt        |

## <a name="sensitivity-label-dlp-policy-matched"></a>DLP-princip matchad med känslighetsetikett

Den här händelsen genereras varje gång en DLP-princip matchas.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Exchange         |Ja       |
|SharePoint Online|Ja          |
|OneDrive |Ja|
|Teams |Ja   |
|Windows 10-enheter         |Ja |
|MAC         |Nej     |
|lokalt         |Nej|
|MCAS     |Nej        | 

Händelserna för Windows 10-enheter (slutpunkt DLP) är:

- fil borttagna
- fil skapad
- fil som kopierats till Urklipp
- fil ändrad
- fil som lästs
- fil utskriven
- filen har bytt namn
- fil som kopierats till nätverksresurs
- fil som används av ej tillkomlig app


## <a name="retention-label-applied"></a>Bevarandeetikett tillämpad 

Den här händelsen genereras varje gång ett dokument utan etikett sätts på etiketten eller om ett e-postmeddelande skickas med en etikett.

- Den fångas när du sparar i Office-program och webbprogram.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Exchange         |Nej       |
|SharePoint Online|Ja          |
|OneDrive |Ja|

## <a name="retention-label-changed"></a>Bevarandeetikett har ändrats

Händelsen genereras varje gång en etikett uppdateras i ett dokument eller e-postmeddelande.

- Filen sparas när den sparas.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Exchange         |Nej       |
|SharePoint Online|Ja          |
|OneDrive |Ja|
 
## <a name="retention-label-removed"></a>Bevarandeetikett borttagen

Händelsen genereras varje gång en etikett tas bort från en fil eller ett dokument.

- Filen sparas när den sparas.

|Source  |Rapporterad i Aktivitetsutforskaren |
|---------|---------| 
|Exchange         |Nej       |
|SharePoint Online|Ja          |
|OneDrive |Ja|


## <a name="known-issues"></a>Kända problem
  
- När den rekommenderade etikettypen visas för en slutanvändare så fångas den inte upp. Men om användaren väljer att använda den rekommenderade etiketten visas etiketten under fältet Hur *används* som *Rekommenderas*  

- Justeringstexten är för närvarande inte tillgänglig vid känslighetsetiketts nedgradering från Sharepoint och OneDrive.  

- Typer av känslig information är för närvarande inte tillgängliga för aktiviteter med automatisk etikett från Word, Excel, PowerPoint och Outlook, samt SharePoint Online och OneDrive.
