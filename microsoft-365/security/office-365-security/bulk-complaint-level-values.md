---
title: Värden på massklagomålsnivå, massutskick, BCL-nivåer, hur BCL fungerar, BCL-klassificeringar, Antispam, Antispam-huvud, massfiltrering av e-post, stoppa massutskick
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Läs mer om BCL-värden (Mass Complain Level) i Office 365.
ms.openlocfilehash: b0eb922323421834eae77b8c5430f1bd8f48c8ee
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807945"
---
# <a name="bulk-complaint-level-values"></a>Värden på massklagomålsnivå

Massanvändare varierar i sina sändningsmönster, innehållsskapande och listförvärvsmetoder. Vissa är bra bulk användare som skickar önskade meddelanden med relevant innehåll till sina abonnenter. Dessa meddelanden genererar få klagomål från mottagare. Andra massutskick skickar oönskade meddelanden som liknar skräppost och genererar många klagomål från mottagare.

Om du vill särskilja dessa typer av massutskick tilldelas meddelanden från massanvändare en BCL-klassificering (Bulk Complaint Level). BCL betyg varierar från 1 till 9 beroende på hur sannolikt bulk mailer är att generera klagomål. En avsändare som har ett betyg på BCL 9 kommer sannolikt att generera många klagomål från mottagare, medan en rating på BCL 3 är osannolikt att generera många klagomål. Microsoft använder både interna och tredje parts källor för att identifiera massutskick och bestämma lämplig BCL. Mer information om det här meddelandehuvudet finns i [Anti-spam-meddelanderubriker](anti-spam-message-headers.md).

Eftersom en massutskicksutskick med en rating på 9 sannolikt kommer att generera klagomål, är standard BCL 7. Detta innebär att bulk post kommer att accepteras tills klagomålet nivå 7 och post kommer inte att accepteras därefter. Ju lägre betyg, desto mindre bulk post accepteras. Om användarna är, och deras arbete är, känslig för massutskick och din BCL är inställd på 4, kommer ingen masspost med en högre BCL än 4 att accepteras.

Du kan använda BCL-värden för att ange önskad nivå för massfiltrering som organisationen kräver genom att följa stegen i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).

I följande tabell beskrivs de BCL-värden som används för närvarande.

|||
|:-----|:-----|
|**BCL-värde**|**Beskrivning**|
|0|Meddelandet kommer inte från en massavsändare.|
|1, 2, 3|Meddelandet kommer från en massavsändare som genererar få klagomål.|
|4, 5, 6, 7|Meddelandet kommer från en massavsändare som genererar ett blandat antal klagomål.|
|8, 9|Meddelandet kommer från en massavsändare som genererar ett stort antal klagomål.|
