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
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952542"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="2ca8c-104">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="2ca8c-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2ca8c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2ca8c-105">**Applies to:**</span></span>
- <span data-ttu-id="2ca8c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ca8c-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="2ca8c-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ca8c-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="2ca8c-108">Med anpassade identifieringar kan du proaktivt övervaka efter och svara på olika händelser och systemhändelser, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="2ca8c-108">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="2ca8c-109">Det här görs möjligt genom anpassningsbara identifieringsregler som automatiskt utlöser aviseringar och svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="2ca8c-109">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="2ca8c-110">Anpassade identifieringar fungerar med [avancerad](advanced-hunting-overview.md)sökning , som ger ett kraftfullt, flexibelt frågespråk som omfattar en omfattande uppsättning händelse- och systeminformation från nätverket.</span><span class="sxs-lookup"><span data-stu-id="2ca8c-110">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="2ca8c-111">Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="2ca8c-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="2ca8c-112">Anpassade identifieringar ger:</span><span class="sxs-lookup"><span data-stu-id="2ca8c-112">Custom detections provide:</span></span>
- <span data-ttu-id="2ca8c-113">Aviseringar för regelbaserade identifieringar som skapats från avancerade sökfrågor</span><span class="sxs-lookup"><span data-stu-id="2ca8c-113">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="2ca8c-114">Automatiska svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="2ca8c-114">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="2ca8c-115">Se även</span><span class="sxs-lookup"><span data-stu-id="2ca8c-115">See also</span></span>
- [<span data-ttu-id="2ca8c-116">Skapa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="2ca8c-116">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="2ca8c-117">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="2ca8c-117">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2ca8c-118">Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ca8c-118">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
