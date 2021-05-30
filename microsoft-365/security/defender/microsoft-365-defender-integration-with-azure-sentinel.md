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
ms.openlocfilehash: b5a53131733d1c7c539676c1d45abe7eabbe2de7
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707354"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="ec9ed-104">Microsoft 365 Defender-integrering med Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="ec9ed-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ec9ed-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ec9ed-105">**Applies to:**</span></span>
- <span data-ttu-id="ec9ed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec9ed-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ec9ed-107">Med Microsoft 365 Defender Connector för Azure Sentinel (förhandsversion) skickas alla Microsoft 365 Defender-incidenter och aviseringsinformation till Azure Sentinel och ser till att incidenterna synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="ec9ed-108">När du lägger till anslutningen strömmas Microsoft 365 alla associerade aviseringar, enheter och relevant information från Microsoft Defender för Slutpunkt, Microsoft Defender för identitet, Microsoft Defender för identitet, Microsoft Defender för Office 365 och Microsoft Cloud App Security till Azure Sentinel som säkerhetsinformation och händelsehanteringsdata (SIEM), vilket ger kontext för att utföra triage- och incidentsvar med &mdash; &mdash; Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="ec9ed-109">I Azure Sentinel förblir incidenterna synkroniserade i båda riktningarna med Microsoft 365 Defender, så att du kan dra nytta av fördelarna med både Microsoft 365 säkerhetscenter och Azure Sentinel i Azure-portalen för undersökning av incidenter och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="ec9ed-110">Så här fungerar det.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-110">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flödet och delning av incidentdata mellan Microsoft 365 Defender och Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="ec9ed-112">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ec9ed-112">Next steps</span></span>

1. <span data-ttu-id="ec9ed-113">Få bättre förståelse för [hur Microsoft 365 Defender-integrering med Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span><span class="sxs-lookup"><span data-stu-id="ec9ed-113">Get a better understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="ec9ed-114">[Anslut data från Microsoft 365 Defender till Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="ec9ed-114">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="ec9ed-115">Se även</span><span class="sxs-lookup"><span data-stu-id="ec9ed-115">See also</span></span>

- [<span data-ttu-id="ec9ed-116">Översikt över incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec9ed-116">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="ec9ed-117">Undersöka incidenter med Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="ec9ed-117">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
