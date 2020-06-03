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
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498357"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="1ca61-104">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="1ca61-104">Custom detections overview</span></span>

<span data-ttu-id="1ca61-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="1ca61-105">**Applies to:**</span></span>
- <span data-ttu-id="1ca61-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="1ca61-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1ca61-107">Med anpassade identifieringar kan du proaktivt övervaka och svara på olika händelser och systemtillstånd, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="1ca61-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="1ca61-108">Detta möjliggörs genom anpassningsbara identifieringsregler som automatiskt utlöser aviseringar samt svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="1ca61-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="1ca61-109">Anpassade identifieringar fungerar med [avancerad jakt](advanced-hunting-overview.md), som ger ett kraftfullt, flexibelt frågespråk som täcker en bred uppsättning händelse- och systeminformation från nätverket.</span><span class="sxs-lookup"><span data-stu-id="1ca61-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="1ca61-110">Du kan ställa in dem så att de körs med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="1ca61-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="1ca61-111">Anpassade identifieringar ger:</span><span class="sxs-lookup"><span data-stu-id="1ca61-111">Custom detections provide:</span></span>
- <span data-ttu-id="1ca61-112">Varningar för regelbaserade identifieringar som skapats från avancerade jaktfrågor</span><span class="sxs-lookup"><span data-stu-id="1ca61-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="1ca61-113">Automatiska svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="1ca61-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="1ca61-114">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="1ca61-114">Related topic</span></span>
- [<span data-ttu-id="1ca61-115">Skapa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="1ca61-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="1ca61-116">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="1ca61-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)