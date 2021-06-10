---
title: Exponeringsresultat i Hantering av hot och säkerhetsrisker
description: Exponeringsresultatet Hantering av hot och säkerhetsrisker hur sårbar organisationen är för hot om cybersäkerhet.
keywords: exponeringspoäng, Microsoft Defender för exponeringsresultat för slutpunkt, Microsoft Defender för exponeringspoäng för slutpunkt tvm, exponeringspoäng för organisation, exponeringsresultat för tvm-organisation, Hantering av hot och säkerhetsrisker, Microsoft Defender för Slutpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcea240fe1dc0ce97a2800391320b04c39c84336
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934111"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="40f30-104">Exponeringsresultat – Hantering av hot och säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="40f30-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40f30-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="40f30-105">**Applies to:**</span></span>

- [<span data-ttu-id="40f30-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="40f30-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="40f30-107">Hot och hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="40f30-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="40f30-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40f30-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="40f30-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="40f30-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="40f30-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="40f30-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="40f30-111">Din exponeringsresultat visas i hantering av säkerhetsrisker [i](tvm-dashboard-insights.md) Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="40f30-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="40f30-112">Den visar hur sårbar organisationen är för hot om cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="40f30-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="40f30-113">Låg exponeringspoäng innebär att enheterna är mindre sårbara för användning.</span><span class="sxs-lookup"><span data-stu-id="40f30-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="40f30-114">Förstå och identifiera takeaways på hög nivå om säkerhetstillstånden i din organisation.</span><span class="sxs-lookup"><span data-stu-id="40f30-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="40f30-115">Identifiera och svara på områden som kräver undersökning eller åtgärd för att förbättra den aktuella statusen.</span><span class="sxs-lookup"><span data-stu-id="40f30-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="40f30-116">Kommunicera med kollegor och ledningen om hur säkerhetsarbetet kommer att påverkas.</span><span class="sxs-lookup"><span data-stu-id="40f30-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="40f30-117">Kortet ger dig en bra bild av exponeringsresultattrenden över tid.</span><span class="sxs-lookup"><span data-stu-id="40f30-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="40f30-118">Alla ökningar i diagrammet ger en visuell indikation om exponering av hot mot cyberhot som du kan undersöka ytterligare.</span><span class="sxs-lookup"><span data-stu-id="40f30-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![Exponeringsresultatkort](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="40f30-120">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="40f30-120">How it works</span></span>

<span data-ttu-id="40f30-121">Exponeringsresultatet delas in i följande nivåer:</span><span class="sxs-lookup"><span data-stu-id="40f30-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="40f30-122">0–29: låg exponeringspoäng</span><span class="sxs-lookup"><span data-stu-id="40f30-122">0–29: low exposure score</span></span>
- <span data-ttu-id="40f30-123">30–69: medelhög exponeringspoäng</span><span class="sxs-lookup"><span data-stu-id="40f30-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="40f30-124">70–100: hög exponeringspoäng</span><span class="sxs-lookup"><span data-stu-id="40f30-124">70–100: high exposure score</span></span>

<span data-ttu-id="40f30-125">Du kan åtgärda problemen baserat på prioriterade säkerhetsrekommendationer [för att](tvm-security-recommendation.md) minska exponeringsresultatet.</span><span class="sxs-lookup"><span data-stu-id="40f30-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="40f30-126">Varje programvara har svagheter som omvandlats till rekommendationer och prioriteras utifrån risker för organisationen.</span><span class="sxs-lookup"><span data-stu-id="40f30-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="40f30-127">Minska risken för exponering av sårbarheter</span><span class="sxs-lookup"><span data-stu-id="40f30-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="40f30-128">Minska exponeringen av hot och risker genom att åtgärda [säkerhetsrekommendationer](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="40f30-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="40f30-129">Gör störst inverkan på exponeringsresultatet genom att åtgärda de viktigaste säkerhetsrekommendationerna, som kan visas i Hantering av hot och säkerhetsrisker [.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="40f30-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="40f30-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="40f30-130">Related topics</span></span>

- [<span data-ttu-id="40f30-131">Översikt över hantering av säkerhetsrisker hot och hot</span><span class="sxs-lookup"><span data-stu-id="40f30-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="40f30-132">Microsoft Secure Score för enheter</span><span class="sxs-lookup"><span data-stu-id="40f30-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="40f30-133">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="40f30-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="40f30-134">Tidlinje för händelse</span><span class="sxs-lookup"><span data-stu-id="40f30-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
