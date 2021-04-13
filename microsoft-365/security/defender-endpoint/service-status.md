---
title: Kontrollera tjänstens hälsa för Microsoft Defender
description: Kontrollera Microsoft Defender för Endpoint-tjänstens hälsa. Kontrollera om tjänsten har problem och granska tidigare problem som har lösts.
keywords: instrumentpanel, tjänst, problem, tjänstens hälsa, aktuell status, statushistorik, sammanfattning av påverkan, preliminär rot, lösning, upplösningstid, förväntad upplösningstid
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1b4545daace5df1a1a9c6e827f7d8f1b522a690c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687631"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="f1f9a-104">Kontrollera tjänstens hälsa för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f1f9a-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f1f9a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f1f9a-105">**Applies to:**</span></span>
- [<span data-ttu-id="f1f9a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1f9a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="f1f9a-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f1f9a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f1f9a-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="f1f9a-109">**Tjänstens** hälsa ger information om aktuell status för Defender för slutpunkt-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="f1f9a-110">Du kan kontrollera att tjänstens hälsa är felfri eller om det finns aktuella problem.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="f1f9a-111">Om det finns problem visas information, till exempel när problemet upptäcktes, vad den preliminära orsaken är och den förväntade upplösningstiden.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="f1f9a-112">Du ser även information om historiska problem som har lösts och information som datum och tid då problemet löstes.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="f1f9a-113">När det inte finns några problem i tjänsten ser du en felfri status.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="f1f9a-114">Du kan visa information om tjänstens hälsa  genom att klicka  på panelen på instrumentpanelen för säkerhetsåtgärder eller välja menyn Tjänstens hälsa i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="f1f9a-115">Sidan **Information om** tjänstens hälsa har följande flikar:</span><span class="sxs-lookup"><span data-stu-id="f1f9a-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="f1f9a-116">**Aktuell status**</span><span class="sxs-lookup"><span data-stu-id="f1f9a-116">**Current status**</span></span>
- <span data-ttu-id="f1f9a-117">**Statushistorik**</span><span class="sxs-lookup"><span data-stu-id="f1f9a-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="f1f9a-118">Aktuell status</span><span class="sxs-lookup"><span data-stu-id="f1f9a-118">Current status</span></span>
<span data-ttu-id="f1f9a-119">På **fliken Aktuell status** visas aktuell status för Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="f1f9a-120">När tjänsten fungerar smidigt visas en felfri tjänsthälsa.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="f1f9a-121">Om några problem har visats visas följande tjänstinformation för att hjälpa dig att få bättre insikt om problemet:</span><span class="sxs-lookup"><span data-stu-id="f1f9a-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="f1f9a-122">Datum och tid för när problemet upptäcktes</span><span class="sxs-lookup"><span data-stu-id="f1f9a-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="f1f9a-123">En kort beskrivning av problemet</span><span class="sxs-lookup"><span data-stu-id="f1f9a-123">A short description of the issue</span></span>
- <span data-ttu-id="f1f9a-124">Uppdateringstid</span><span class="sxs-lookup"><span data-stu-id="f1f9a-124">Update time</span></span>
- <span data-ttu-id="f1f9a-125">Sammanfattning av påverkan</span><span class="sxs-lookup"><span data-stu-id="f1f9a-125">Summary of impact</span></span>
- <span data-ttu-id="f1f9a-126">Preliminär orsak</span><span class="sxs-lookup"><span data-stu-id="f1f9a-126">Preliminary root cause</span></span>
- <span data-ttu-id="f1f9a-127">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f1f9a-127">Next steps</span></span>
- <span data-ttu-id="f1f9a-128">Förväntad upplösningstid</span><span class="sxs-lookup"><span data-stu-id="f1f9a-128">Expected resolution time</span></span>

<span data-ttu-id="f1f9a-129">Uppdateringar av ett problems förlopp återspeglas på sidan allt eftersom problemet löses.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="f1f9a-130">Du ser uppdateringar av information, till exempel en uppdaterad uppskattningstid för upplösning eller nästa steg.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="f1f9a-131">När ett problem åtgärdas registreras det på **fliken Statushistorik.**</span><span class="sxs-lookup"><span data-stu-id="f1f9a-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="f1f9a-132">Statushistorik</span><span class="sxs-lookup"><span data-stu-id="f1f9a-132">Status history</span></span>
<span data-ttu-id="f1f9a-133">Fliken **Statushistorik** visar alla historiska problem som har setts och lösts.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="f1f9a-134">Du ser information om de lösta problemen tillsammans med annan information som inkluderades medan den löstes.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="f1f9a-135">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="f1f9a-135">Related topic</span></span>
- [<span data-ttu-id="f1f9a-136">Visa instrumentpanelen för säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="f1f9a-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
