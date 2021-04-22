---
title: Översikt över anpassade identifieringar i Microsoft 365 Defender
description: Förstå hur du kan använda avancerad sökning för att skapa anpassade identifieringar och generera aviseringar
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bf635ed03cb0d99d54fc94b622bf244447b32a80
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935707"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="b8193-104">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="b8193-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b8193-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b8193-105">**Applies to:**</span></span>
- <span data-ttu-id="b8193-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8193-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b8193-107">Med anpassade identifieringar kan du proaktivt övervaka efter och svara på olika händelser och systemhändelser, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="b8193-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="b8193-108">Det här görs möjligt genom anpassningsbara identifieringsregler som automatiskt utlöser aviseringar och svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="b8193-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="b8193-109">Anpassade identifieringar fungerar med [avancerad](advanced-hunting-overview.md)sökning , som ger ett kraftfullt, flexibelt frågespråk som omfattar en omfattande uppsättning händelse- och systeminformation från nätverket.</span><span class="sxs-lookup"><span data-stu-id="b8193-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="b8193-110">Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="b8193-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="b8193-111">Anpassade identifieringar ger:</span><span class="sxs-lookup"><span data-stu-id="b8193-111">Custom detections provide:</span></span>
- <span data-ttu-id="b8193-112">Aviseringar för regelbaserade identifieringar som skapats från avancerade sökfrågor</span><span class="sxs-lookup"><span data-stu-id="b8193-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="b8193-113">Automatiska svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="b8193-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="b8193-114">Se även</span><span class="sxs-lookup"><span data-stu-id="b8193-114">See also</span></span>
- [<span data-ttu-id="b8193-115">Skapa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="b8193-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="b8193-116">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="b8193-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b8193-117">Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b8193-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
