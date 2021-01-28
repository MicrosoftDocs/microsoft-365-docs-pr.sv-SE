---
title: Fixa möjlig inblick i e-postslingan
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur du använder korrigerings filen för möjlig e-post som inblickas i instrument panelen för e-postflöde i säkerhets & efterlevnad för att identifiera och åtgärda e-postloopar i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029900"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Åtgärda eventuell e-postloop inblick i säkerhets & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


E-postloopar är felaktiga på grund av följande:

- De slösar system resurserna.
- De förbrukar organisationens kvot för e-postvolym.
- De skickar förvirrande rapporter (kallas även NDR eller studs meddelanden) till de ursprungliga avsändarna.

Den **åtgärd för möjlig e-post** som är inblick i **Rekommenderad för dig** -området i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & för regelefterlevnad](https://protection.office.com) meddelar dig när en e-postloop upptäcks i din organisation.

Denna inblick visas bara efter det att villkoret har identifierats (om du inte har några e-postloopar visas inte inblicken).

![Åtgärda regler för långsam e-postflöde inblick i det rekommenderade för dig-området på instrument panelen för e-postflöde](../../media/mfi-fix-possible-mail-loop.png)

När du klickar på **Visa information** i widgeten visas en utfällbar lista med mer information:

- **Domain**
- **Antal meddelanden**: du kan klicka på **Visa exempel meddelanden** för att se resultatet av [meddelande spårningen](message-trace-scc.md) för ett urval av de meddelanden som påverkade slingan.
- **Domän typ**"till exempel auktoritär eller icke-auktoritativ.
- **MX-post**:**värd-och** **prioritets** värden för MX-posten för domänen.
- **Upprepa orsaken** och **hur du åtgärdar**: vi identifierar de vanligaste e-postlösningarna och ger rekommenderade åtgärder för att åtgärda slingan.

![Den utfällbara informationen som visas när du klickar på Visa information om att åtgärda eventuella problem med e-post](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Se även

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
