---
title: Registreringsverktyg och -metoder för Windows 10-enheter
description: Introducera Windows 10-enheter så att de kan skicka sensordata till Microsoft Defender ATP-sensorn
keywords: Hantera Windows 10-enheter, grupprincip, slutpunktskonfigurationshanteraren, hantering av mobila enheter, lokalt skript, gp, sccm, mdm, intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165543"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="c42ac-104">Registreringsverktyg och -metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="c42ac-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c42ac-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c42ac-105">**Applies to:**</span></span>
- [<span data-ttu-id="c42ac-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c42ac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c42ac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c42ac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="c42ac-108">Microsoft 365 Endpoint – dataförlustskydd (DLP)</span><span class="sxs-lookup"><span data-stu-id="c42ac-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="c42ac-109">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c42ac-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c42ac-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c42ac-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c42ac-111">Enheter i organisationen måste vara konfigurerade så att Defender för slutpunktstjänsten kan hämta sensordata från dem.</span><span class="sxs-lookup"><span data-stu-id="c42ac-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="c42ac-112">Det finns olika metoder och distributionsverktyg som du kan använda för att konfigurera enheter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="c42ac-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="c42ac-113">Följande distributionsverktyg och -metoder stöds:</span><span class="sxs-lookup"><span data-stu-id="c42ac-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="c42ac-114">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="c42ac-114">Group Policy</span></span>
- <span data-ttu-id="c42ac-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c42ac-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="c42ac-116">Hantering av mobila enheter (inklusive Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="c42ac-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="c42ac-117">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="c42ac-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c42ac-118">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="c42ac-118">In this section</span></span>
<span data-ttu-id="c42ac-119">Ämne</span><span class="sxs-lookup"><span data-stu-id="c42ac-119">Topic</span></span> | <span data-ttu-id="c42ac-120">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c42ac-120">Description</span></span>
:---|:---
[<span data-ttu-id="c42ac-121">Introducera Windows 10-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="c42ac-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="c42ac-122">Använd Grupprincip för att distribuera konfigurationspaketet på enheter.</span><span class="sxs-lookup"><span data-stu-id="c42ac-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="c42ac-123">Introducera Windows-enheter med Hjälp av Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c42ac-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="c42ac-124">Du kan använda antingen Microsoft Endpoint Manager (current branch) version 1606 eller Microsoft Endpoint Manager (current branch) version 1602 eller tidigare för att distribuera konfigurationspaket på enheter.</span><span class="sxs-lookup"><span data-stu-id="c42ac-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="c42ac-125">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="c42ac-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="c42ac-126">Använd Verktyg för hantering av mobila enheter eller Microsoft Intune för att distribuera konfigurationspaketet på enheten.</span><span class="sxs-lookup"><span data-stu-id="c42ac-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="c42ac-127">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="c42ac-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="c42ac-128">Lär dig hur du använder det lokala skriptet för att distribuera konfigurationspaketet på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="c42ac-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="c42ac-129">Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)</span><span class="sxs-lookup"><span data-stu-id="c42ac-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="c42ac-130">Lär dig hur du använder konfigurationspaketet för att konfigurera VDI-enheter.</span><span class="sxs-lookup"><span data-stu-id="c42ac-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="c42ac-131">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c42ac-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c42ac-132">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c42ac-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
