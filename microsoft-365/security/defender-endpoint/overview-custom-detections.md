---
title: Översikt över anpassade identifieringar i Microsoft Defender ATP
ms.reviewer: ''
description: Förstå hur du kan använda avancerad sökning för att skapa anpassade identifieringar och generera aviseringar
keywords: anpassade identifieringar, aviseringar, identifieringsregler, avancerad sökning, sökning, fråga, svarsåtgärder, intervall, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c5de642d2fd22301b5cef1cf3674e60529455d5e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186923"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="faa1d-104">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="faa1d-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="faa1d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="faa1d-105">**Applies to:**</span></span>
- [<span data-ttu-id="faa1d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="faa1d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="faa1d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="faa1d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="faa1d-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="faa1d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="faa1d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="faa1d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="faa1d-110">Med anpassade identifieringar kan du proaktivt övervaka för och svara på olika händelser och systemhändelser, inklusive misstänkt intrångsaktivitet och felkonfigurerade enheter.</span><span class="sxs-lookup"><span data-stu-id="faa1d-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="faa1d-111">Du kan göra detta med anpassningsbara identifieringsregler som automatiskt utlöser aviseringar och svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="faa1d-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="faa1d-112">Anpassade identifieringar fungerar med [avancerad](advanced-hunting-overview.md)sökning , som ger ett kraftfullt, flexibelt frågespråk som omfattar en omfattande uppsättning händelse- och systeminformation från nätverket.</span><span class="sxs-lookup"><span data-stu-id="faa1d-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="faa1d-113">Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="faa1d-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="faa1d-114">Anpassade identifieringar ger:</span><span class="sxs-lookup"><span data-stu-id="faa1d-114">Custom detections provide:</span></span>
- <span data-ttu-id="faa1d-115">Aviseringar för regelbaserade identifieringar som skapats från avancerade sökfrågor</span><span class="sxs-lookup"><span data-stu-id="faa1d-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="faa1d-116">Automatiska svarsåtgärder som gäller för filer och enheter</span><span class="sxs-lookup"><span data-stu-id="faa1d-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="faa1d-117">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="faa1d-117">Related topics</span></span>
- [<span data-ttu-id="faa1d-118">Skapa identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="faa1d-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="faa1d-119">Visa och hantera identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="faa1d-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="faa1d-120">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="faa1d-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
