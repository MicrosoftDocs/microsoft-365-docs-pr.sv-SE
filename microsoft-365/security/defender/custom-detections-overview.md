---
title: Översikt över anpassade identifieringar i Microsoft 365 Defender
description: Förstå hur du kan använda avancerad sökning för att skapa anpassade identifieringar och generera aviseringar
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4a4b601b5f8b9a21d7e7260fcadf9fecd0e37c5b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068970"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="a6cc1-104">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="a6cc1-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a6cc1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a6cc1-105">**Applies to:**</span></span>
- <span data-ttu-id="a6cc1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6cc1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a6cc1-107">Med anpassade identifieringar kan du proaktivt övervaka efter och svara på olika händelser och systemhändelser, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="a6cc1-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="a6cc1-108">Det här görs möjligt genom anpassningsbara identifieringsregler som automatiskt utlöser aviseringar och svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="a6cc1-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="a6cc1-109">Anpassade identifieringar fungerar med [avancerad](advanced-hunting-overview.md)sökning , som ger ett kraftfullt, flexibelt frågespråk som omfattar en omfattande uppsättning händelse- och systeminformation från nätverket.</span><span class="sxs-lookup"><span data-stu-id="a6cc1-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="a6cc1-110">Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="a6cc1-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="a6cc1-111">Anpassade identifieringar ger:</span><span class="sxs-lookup"><span data-stu-id="a6cc1-111">Custom detections provide:</span></span>
- <span data-ttu-id="a6cc1-112">Aviseringar för regelbaserade identifieringar som skapats från avancerade sökfrågor</span><span class="sxs-lookup"><span data-stu-id="a6cc1-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="a6cc1-113">Automatiska svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="a6cc1-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="a6cc1-114">Se även</span><span class="sxs-lookup"><span data-stu-id="a6cc1-114">See also</span></span>
- [<span data-ttu-id="a6cc1-115">Skapa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="a6cc1-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="a6cc1-116">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="a6cc1-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a6cc1-117">Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a6cc1-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
