---
title: Översikt över anpassade identifieringar i Microsoft 365 Defender
description: Förstå hur du kan använda avancerad sökning för att skapa anpassade identifieringar och generera aviseringar
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, anpassade identifieringar, schema, kusto, microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928814"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="8b05c-104">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="8b05c-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8b05c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8b05c-105">**Applies to:**</span></span>
- <span data-ttu-id="8b05c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b05c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8b05c-107">Med anpassade identifieringar kan du proaktivt övervaka för och svara på olika händelser och systemhändelser, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="8b05c-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="8b05c-108">Det här görs möjligt genom anpassningsbara identifieringsregler som automatiskt utlöser aviseringar och svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="8b05c-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="8b05c-109">Anpassade identifieringar fungerar med [avancerad](advanced-hunting-overview.md)sökning, som ger ett kraftfullt, flexibelt frågespråk som täcker en omfattande uppsättning händelse- och systeminformation från nätverket.</span><span class="sxs-lookup"><span data-stu-id="8b05c-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="8b05c-110">Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="8b05c-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="8b05c-111">Anpassade identifieringar ger:</span><span class="sxs-lookup"><span data-stu-id="8b05c-111">Custom detections provide:</span></span>
- <span data-ttu-id="8b05c-112">Varningar för regelbaserade identifieringar byggda av avancerade sökningsfrågor</span><span class="sxs-lookup"><span data-stu-id="8b05c-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="8b05c-113">Automatiska svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="8b05c-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="8b05c-114">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="8b05c-114">Related topic</span></span>
- [<span data-ttu-id="8b05c-115">Skapa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="8b05c-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="8b05c-116">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="8b05c-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
