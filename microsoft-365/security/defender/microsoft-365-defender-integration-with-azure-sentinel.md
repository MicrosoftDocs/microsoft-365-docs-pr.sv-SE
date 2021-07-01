---
title: Microsoft 365 Defender-integrering med Azure Sentinel
description: Använd Azure Sentinel som SIEM för Microsoft 365 Defender och händelser.
keywords: incidenter, aviseringar, undersöker, analyserar, svar, korrelation, attack, datorer, enheter, användare, identiteter, identitet, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b9a9a6381c93e2d252f75710adc206868c0a5546
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229917"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Defender-integrering med Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Den Microsoft 365 Defender för Azure Sentinel (förhandsversion) skickar alla Microsoft 365 Defender och aviseringar till Azure Sentinel och synkroniserar incidenterna. 

När du lägger till anslutningen strömmas Microsoft 365 Defender-incidenter som inkluderar alla associerade aviseringar, enheter och relevant information som tas emot från Microsoft Defender för Endpoint, Microsoft Defender för identitet, Microsoft Defender för Office 365 och Microsoft Cloud App Security till Azure Sentinel som säkerhetsinformations- och händelsehanteringsdata (SIEM), vilket ger kontext för att utföra triage- och incidentsvar med &mdash; &mdash; Azure Sentinel. 

När du väl har gjort detta i Azure Sentinel förblir incidenterna synkroniserade i båda riktningarna med Microsoft 365 Defender, så att du kan dra nytta av fördelarna med både säkerhetscentret i Microsoft 365 och Azure Sentinel i Azure-portalen för undersökning av incidenter och åtgärder.

Titta på den här korta översikten över Azure Sentinel-integrering Microsoft 365 Defender (4 minuter).

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


Så här fungerar det.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flöde och delning av incidentdata mellan Microsoft 365 Defender och Azure Sentinel":::

## <a name="next-steps"></a>Nästa steg

1. Få en djupare förståelse för [Microsoft 365 Defender integration med Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [Anslut data från Microsoft 365 Defender till Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>Se även

- [Översikt över incidenter i Microsoft 365 Defender](incidents-overview.md)
- [Undersöka incidenter med Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
