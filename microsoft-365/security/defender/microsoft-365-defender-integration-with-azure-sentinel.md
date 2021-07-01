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
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="4296e-104">Microsoft 365 Defender-integrering med Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="4296e-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4296e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4296e-105">**Applies to:**</span></span>
- <span data-ttu-id="4296e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4296e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4296e-107">Den Microsoft 365 Defender för Azure Sentinel (förhandsversion) skickar alla Microsoft 365 Defender och aviseringar till Azure Sentinel och synkroniserar incidenterna.</span><span class="sxs-lookup"><span data-stu-id="4296e-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="4296e-108">När du lägger till anslutningen strömmas Microsoft 365 Defender-incidenter som inkluderar alla associerade aviseringar, enheter och relevant information som tas emot från Microsoft Defender för Endpoint, Microsoft Defender för identitet, Microsoft Defender för Office 365 och Microsoft Cloud App Security till Azure Sentinel som säkerhetsinformations- och händelsehanteringsdata (SIEM), vilket ger kontext för att utföra triage- och incidentsvar med &mdash; &mdash; Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="4296e-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="4296e-109">När du väl har gjort detta i Azure Sentinel förblir incidenterna synkroniserade i båda riktningarna med Microsoft 365 Defender, så att du kan dra nytta av fördelarna med både säkerhetscentret i Microsoft 365 och Azure Sentinel i Azure-portalen för undersökning av incidenter och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4296e-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="4296e-110">Titta på den här korta översikten över Azure Sentinel-integrering Microsoft 365 Defender (4 minuter).</span><span class="sxs-lookup"><span data-stu-id="4296e-110">Watch this short overview of Azure Sentinel integration with Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


<span data-ttu-id="4296e-111">Så här fungerar det.</span><span class="sxs-lookup"><span data-stu-id="4296e-111">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flöde och delning av incidentdata mellan Microsoft 365 Defender och Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="4296e-113">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4296e-113">Next steps</span></span>

1. <span data-ttu-id="4296e-114">Få en djupare förståelse för [Microsoft 365 Defender integration med Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)</span><span class="sxs-lookup"><span data-stu-id="4296e-114">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="4296e-115">[Anslut data från Microsoft 365 Defender till Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="4296e-115">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="4296e-116">Se även</span><span class="sxs-lookup"><span data-stu-id="4296e-116">See also</span></span>

- [<span data-ttu-id="4296e-117">Översikt över incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4296e-117">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="4296e-118">Undersöka incidenter med Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="4296e-118">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
