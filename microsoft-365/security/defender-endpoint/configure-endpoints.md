---
title: Registreringsverktyg och -metoder för Windows 10-enheter
description: Introducera Windows 10-enheter så att de kan skicka sensordata till Microsoft Defender för slutpunkts sensor
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
ms.openlocfilehash: f1ef2670a1ca749e0a2f1ebc96300d4eca043bf8
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892835"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="a6883-104">Registreringsverktyg och -metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="a6883-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a6883-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a6883-105">**Applies to:**</span></span>
- [<span data-ttu-id="a6883-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a6883-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a6883-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6883-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="a6883-108">Microsoft 365 Endpoint – dataförlustskydd (DLP)</span><span class="sxs-lookup"><span data-stu-id="a6883-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="a6883-109">Microsoft 365 Insider-riskhantering</span><span class="sxs-lookup"><span data-stu-id="a6883-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="a6883-110">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a6883-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a6883-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a6883-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="a6883-112">Enheter i organisationen måste vara konfigurerade så att Defender för slutpunktstjänsten kan hämta sensordata från dem.</span><span class="sxs-lookup"><span data-stu-id="a6883-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="a6883-113">Det finns olika metoder och distributionsverktyg som du kan använda för att konfigurera enheter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="a6883-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="a6883-114">Följande distributionsverktyg och -metoder stöds:</span><span class="sxs-lookup"><span data-stu-id="a6883-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="a6883-115">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="a6883-115">Group Policy</span></span>
- <span data-ttu-id="a6883-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a6883-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="a6883-117">Hantering av mobila enheter (inklusive Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="a6883-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="a6883-118">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="a6883-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a6883-119">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="a6883-119">In this section</span></span>
<span data-ttu-id="a6883-120">Ämne</span><span class="sxs-lookup"><span data-stu-id="a6883-120">Topic</span></span> | <span data-ttu-id="a6883-121">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a6883-121">Description</span></span>
:---|:---
[<span data-ttu-id="a6883-122">Introducera Windows 10-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="a6883-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="a6883-123">Använd Grupprincip för att distribuera konfigurationspaketet på enheter.</span><span class="sxs-lookup"><span data-stu-id="a6883-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="a6883-124">Introducera Windows-enheter med Hjälp av Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a6883-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="a6883-125">Du kan använda antingen Microsoft Endpoint Manager (current branch) version 1606 eller Microsoft Endpoint Manager (current branch) version 1602 eller tidigare för att distribuera konfigurationspaket på enheter.</span><span class="sxs-lookup"><span data-stu-id="a6883-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="a6883-126">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="a6883-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="a6883-127">Använd Verktyg för hantering av mobila enheter eller Microsoft Intune för att distribuera konfigurationspaketet på enheten.</span><span class="sxs-lookup"><span data-stu-id="a6883-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="a6883-128">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="a6883-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="a6883-129">Lär dig hur du använder det lokala skriptet för att distribuera konfigurationspaketet på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="a6883-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="a6883-130">Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="a6883-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="a6883-131">Lär dig hur du använder konfigurationspaketet för att konfigurera VDI-enheter.</span><span class="sxs-lookup"><span data-stu-id="a6883-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="a6883-132">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a6883-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a6883-133">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a6883-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
