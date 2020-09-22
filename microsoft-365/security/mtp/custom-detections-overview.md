---
title: Översikt över anpassade identifieringar i skydd mot Microsoft Threat
description: Förstå hur du kan använda avancerad jakt för att skapa anpassade identifieringar och skapa aviseringar
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, anpassade identifieringar, schema, kusto, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 28d6cca20c8b386d5e6f7f39b80264a39f88ec55
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199471"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="6f501-104">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="6f501-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6f501-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6f501-105">**Applies to:**</span></span>
- <span data-ttu-id="6f501-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="6f501-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6f501-107">Med anpassade identifieringar kan du proaktivt övervaka för att visa och svara på olika händelser och system tillstånd, inklusive misstänkt överträdelse aktivitet och felkonfigurerade slut punkter.</span><span class="sxs-lookup"><span data-stu-id="6f501-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="6f501-108">Det här är möjligt genom anpassningsbara identifierings regler som automatiskt aktiverar notifieringar och svars åtgärder.</span><span class="sxs-lookup"><span data-stu-id="6f501-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="6f501-109">Anpassade identifieringar fungerar med [Avancerad jakt](advanced-hunting-overview.md), som innehåller ett kraftfullt och flexibelt frågespråk som täcker en bred uppsättning händelser och system information från ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="6f501-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="6f501-110">Du kan ange att de ska köras med jämna mellanrum, skapa aviseringar och vidta åtgärder när det finns träffar.</span><span class="sxs-lookup"><span data-stu-id="6f501-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="6f501-111">Anpassade identifierings alternativ:</span><span class="sxs-lookup"><span data-stu-id="6f501-111">Custom detections provide:</span></span>
- <span data-ttu-id="6f501-112">Aviseringar för regelbaserade identifieringar baserade på avancerade jakt frågor</span><span class="sxs-lookup"><span data-stu-id="6f501-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="6f501-113">Automatiska svars åtgärder</span><span class="sxs-lookup"><span data-stu-id="6f501-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="6f501-114">Närliggande ämne</span><span class="sxs-lookup"><span data-stu-id="6f501-114">Related topic</span></span>
- [<span data-ttu-id="6f501-115">Skapa och hantera anpassade identifierings regler</span><span class="sxs-lookup"><span data-stu-id="6f501-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="6f501-116">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="6f501-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
