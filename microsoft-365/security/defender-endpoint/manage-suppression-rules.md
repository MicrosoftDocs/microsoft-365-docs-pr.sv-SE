---
title: Hantera regler för Microsoft Defender för slutpunktsslutpunkter
description: Du kan behöva förhindra att aviseringar visas i portalen genom att använda regler som gäller här. Lär dig hur du hanterar regler som gäller i Microsoft Defender för Endpoint.
keywords: hantera hantera hantera regler, regelnamn, omfattning, åtgärd, aviseringar, aktivera, inaktivera
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f1549512a02fe3af71d32c6b33c69cc705de99a8
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862133"
---
# <a name="manage-suppression-rules"></a>Hantera undertryckande regler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Det kan finnas scenarier där du behöver dölja aviseringar från att visas i portalen. Du kan skapa regelregler för specifika aviseringar som är kända som obesvarade, till exempel kända verktyg eller processer i organisationen. Mer information om hur du ignorerar aviseringar finns i [Utelämna aviseringar.](manage-alerts.md)

Du kan visa en lista över alla regler och hantera dem på ett och samma ställe. Du kan också aktivera eller inaktivera en aviseringsregel.


1. I navigeringsfönstret väljer du Inställningar  >  **Avisering – sekretess.** Listan över regelregler som användare i organisationen har skapat visas.

2. Välj en regel genom att klicka på kryssrutan bredvid regelnamnet.

3. Klicka **på Aktivera regel,** **Redigera regel** eller Ta **bort regel.** När du gör ändringar i en regel kan du välja att släppa aviseringar som redan har ignorerats, oavsett om aviseringarna matchar de nya villkoren eller inte. 


## <a name="view-details-of-a-suppression-rule"></a>Visa information om en regel för en regel

1. I navigeringsfönstret väljer du Inställningar  >  **Avisering – sekretess.** Listan över regelregler som användare i organisationen har skapat visas.

2. Klicka på ett regelnamn. Information om regeln visas. Du ser regeldetaljer som status, omfattning, åtgärd, antal matchande aviseringar, skapat av och datum då regeln skapades. Du kan också visa associerade aviseringar och regelvillkor.

## <a name="related-topics"></a>Relaterade ämnen

- [Hantera varningar](manage-alerts.md)
