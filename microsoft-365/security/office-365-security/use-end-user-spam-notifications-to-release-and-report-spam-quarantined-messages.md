---
title: Använda skräppostmeddelanden för slutanvändare för att släppa och rapportera skräppostmeddelanden i karantän
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: 'Användare som ser ett skräppostmeddelande från slutanvändaren om e-post i karantän kan vidta dessa åtgärder i meddelandena. '
ms.openlocfilehash: 4d53e4866733ba0d3de96f068297a342c134e5ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811488"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a>Använda skräppostmeddelanden för slutanvändare för att släppa och rapportera skräppostmeddelanden i karantän

Om administratören aktiverar skräppostmeddelanden för slutanvändare får du ett meddelande om meddelanden som innehåller meddelanden som är avsedda för postlådan och som identifierades som skräppost och i stället sattes i karantän. Det här meddelandet innehåller antalet meddelanden i karantän i skräppost och datum och tid (i universell koordinerad tid (UTC)) för det senaste meddelandet i listan. I den här listan kan du visa följande information om varje meddelande:

- **Avsändare**: Avsändarens namn och e-postadress för det i karantänmeddelandet.

- **Ämne**: Ämnesradens text i det i karantänsmeddelandet.

- **Datum**: Datum och tid (i UTC) som meddelandet sattes i karantän.

- **Storlek:** Storleken på det i karantänmeddelandet, i kbs (kilobyte).

Du kan utföra följande åtgärder för varje meddelande:

- **Släpp till Inkorgen:** Om du klickar på den här länken skickas meddelandet till inkorgen där du kan visa det.

- **Rapport som inte skräp:** Klicka på denna länk skickar en kopia av meddelandet till Microsoft för analys. Skräppostteamet utvärderar och analyserar meddelandet och justerar reglerna för skräppostfilter så att meddelandet går igenom, beroende på analysresultaten.

> [!NOTE]
> Meddelanden som sätts i karantän på grund av en e-postflödesregel (kallas även a) ingår inte i meddelanden om skräppost till slutanvändaren i karantän. Endast skräppostmeddelanden i karantän visas. <br/><br/>  Du kan bara släppa ett meddelande och rapportera det som ett falskt positivt (inte skräppost) en gång.
