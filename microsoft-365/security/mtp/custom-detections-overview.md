---
title: Översikt över anpassade identifieringar i Microsoft Threat Protection
description: Förstå hur du kan använda avancerad jakt för att skapa anpassade identifieringar och generera aviseringar
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade upptäckter, schema, kusto, microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a9ba61650b69e3c42506735c90ae05b917a53209
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931750"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="985bf-104">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="985bf-104">Custom detections overview</span></span>

<span data-ttu-id="985bf-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="985bf-105">**Applies to:**</span></span>
- <span data-ttu-id="985bf-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="985bf-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="985bf-107">Med anpassade identifieringar kan du proaktivt övervaka och svara på olika händelser och systemtillstånd, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="985bf-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="985bf-108">Detta möjliggörs genom anpassningsbara identifieringsregler som automatiskt utlöser aviseringar samt svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="985bf-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="985bf-109">Anpassade identifieringar fungerar med [avancerad jakt](advanced-hunting-overview.md), som ger ett kraftfullt, flexibelt frågespråk som täcker en bred uppsättning händelse- och systeminformation från nätverket.</span><span class="sxs-lookup"><span data-stu-id="985bf-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="985bf-110">Du kan ställa in dem så att de körs med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="985bf-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="985bf-111">Anpassade identifieringar ger:</span><span class="sxs-lookup"><span data-stu-id="985bf-111">Custom detections provide:</span></span>
- <span data-ttu-id="985bf-112">Varningar för regelbaserade identifieringar som skapats från avancerade jaktfrågor</span><span class="sxs-lookup"><span data-stu-id="985bf-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="985bf-113">Automatiska svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="985bf-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="985bf-114">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="985bf-114">Related topic</span></span>
- [<span data-ttu-id="985bf-115">Skapa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="985bf-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="985bf-116">Avancerad jaktöversikt</span><span class="sxs-lookup"><span data-stu-id="985bf-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)