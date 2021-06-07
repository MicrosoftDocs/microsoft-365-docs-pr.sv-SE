---
title: Microsoft 365 Defender-integrering med Azure Sentinel
description: Använd Azure Sentinel som SIEM för Microsoft 365 Defender-incidenter och -händelser.
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
ms.openlocfilehash: 7d9cff584f35c39544034501c607b7156a0f1bf2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782927"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Defender-integrering med Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Med Microsoft 365 Defender Connector för Azure Sentinel (förhandsversion) skickas alla Microsoft 365 Defender-incidenter och aviseringsinformation till Azure Sentinel och ser till att incidenterna synkroniseras. 

När du lägger till anslutningen strömmas Microsoft 365 alla associerade aviseringar, enheter och relevant information från Microsoft Defender för Slutpunkt, Microsoft Defender för identitet, Microsoft Defender för identitet, Microsoft Defender för Office 365 och Microsoft Cloud App Security till Azure Sentinel som säkerhetsinformation och händelsehanteringsdata (SIEM), vilket ger kontext för att utföra triage- och incidentsvar med &mdash; &mdash; Azure Sentinel. 

I Azure Sentinel förblir incidenterna synkroniserade i båda riktningarna med Microsoft 365 Defender, så att du kan dra nytta av fördelarna med både Microsoft 365 säkerhetscenter och Azure Sentinel i Azure-portalen för undersökning av incidenter och åtgärder.

Så här fungerar det.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flödet och delning av incidentdata mellan Microsoft 365 Defender och Azure Sentinel":::

## <a name="next-steps"></a>Nästa steg

1. Få en djupare förståelse för [Microsoft 365 Defender-integrering med Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [Anslut data från Microsoft 365 Defender till Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>Se även

- [Översikt över incidenter i Microsoft 365 Defender](incidents-overview.md)
- [Undersöka incidenter med Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
