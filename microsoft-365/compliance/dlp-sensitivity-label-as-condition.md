---
title: Använda känslighetsetiketter som villkor i DLP-principer
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: lära dig om tjänsterna och objekttyperna som du kan använda känslighetsetiketter som villkor i DLP-principer
ms.openlocfilehash: 19bd80de225f703b5c280163e94826498fa097bd
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162748"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a>Använda känslighetsetiketter som villkor i DLP-principer

Du kan använda [känslighetsetiketter](sensitivity-labels.md) som ett villkor i DLP-principerna för dessa platser:

- E-postmeddelanden från Exchange Online
- SharePoint Online
- OneDrive för företag-webbplatser
- Windows 10-enheter

Känslighetsetiketter visas som ett alternativ i listan **Innehåll innehåller**.

> [!div class="mx-imgBorder"]
> ![känslighetsetikett som ett villkor](../media/dlp-sensitivity-label-as-a-condition.png)

> [!IMPORTANT]
> **Känslighetsetiketter** som ett villkor är inte tillgängligt om du har markerat **Teams chatt- och kanalmeddelanden** som en plats för att tillämpa DLP-principen.


## <a name="supported-items-scenarios-and-policy-tips"></a>Objekt, scenarier och principtips som stöds

Du kan använda känslighetsetiketter som villkor för de här objekten och i dessa scenarier.

### <a name="supported-items"></a>Objekt som stöds:

|Tjänst  |Objekttyp  |Tillgängligt för principtips  |Verkställbar  |
|---------|---------|---------|---------|
|Exchange    |e-postmeddelande         |ja         |ja         |
|Exchange    |e-postbilaga         |nej *         |ja *         |
|SharePoint Online     |object i SharePoint Online         |ja         |ja         |
|OneDrive för företag     |objekt         |ja         |ja         |
|Teams     |Teams och kanalmeddelanden         |ej tillämpligt         |ej tillämpligt         |
|Teams     |bifogade filer         |ja **         |ja **         |
|Windows 10-enheter     |objekt         |ja         |ja         |
|MCAS (förhandsversion) |objekt         |ja         |ja         |

\* DLP-identifiering och tillämpning av känslighetsetiketter för e-postmeddelanden och bilagor stöds under överföringen. Det är inte DLP-principtips för känslighetsetiketter för e-postbilagor.

\** Bifogade filer som skickas i Teams över 1:1 chatt eller kanaler laddas automatiskt upp till OneDrive för företag och SharePoint. Så om SharePoint Online eller OneDrive för företag ingår som platser i DLP-principen inkluderas etiketterade bifogade filer som skickas i Teams automatiskt inom ramen för detta villkor. Teams som en plats behöver inte väljas i DLP-principen.

### <a name="supported-scenarios"></a>Scenarier som stöds

- DLP-administratören kan se en lista över alla känslighetsetiketter i klientorganisationen när de väljer att inkludera en eller flera känslighetsetiketter som ett villkor.

- Användningen av känslighetsetiketter som ett villkor stöds i alla arbetsbelastningar som anges i supportmatrisen ovan.

- DLP-principtips kommer att fortsätta att visas över arbetsbelastningar (förutom Outlook Win32) för DLP-principer som innehåller känslighetsetiketten som ett villkor.

- Känslighetsetiketter visas också som en del av e-postmeddelandet för incidentrapporten om en DLP-princip med känslighetsetiketter matchas som ett villkor.

- Information om känslighetsetiketter visas också i granskningsloggen för DLP-regeln för en matchning av DLP-princip som innehåller känslighetsetiketten som ett villkor.


### <a name="support-policy-tips"></a>Principtips som stöds


|Arbetsbelastning  |Principtips som stöds/inte stöds  |
|---------|---------|
|OWA |    stöds     |
|Outlook Win 32    |  stöds inte       |
|SharePoint   |   stöds      |
|OneDrive för företag    |    stöds     |
|slutpunktsenheter   |  stöds inte       |
