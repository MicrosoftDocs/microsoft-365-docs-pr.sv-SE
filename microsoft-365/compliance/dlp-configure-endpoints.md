---
title: Registreringsverktyg och -metoder för Windows 10-enheter
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Introducera Windows 10 enheter så att de kan skicka sensordata till Microsoft 365 efterlevnadslösningar
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162005"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="b9a32-103">Registreringsverktyg och -metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="b9a32-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="b9a32-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b9a32-104">**Applies to:**</span></span>
- [<span data-ttu-id="b9a32-105">Microsoft 365 Dataförlustskydd i slutpunkt (DLP)</span><span class="sxs-lookup"><span data-stu-id="b9a32-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="b9a32-106">Enheter i organisationen måste vara konfigurerade så att Microsoft 365 dataförlustskydd för slutpunkten kan få sensordata från dem.</span><span class="sxs-lookup"><span data-stu-id="b9a32-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="b9a32-107">Det finns olika metoder och distributionsverktyg som du kan använda för att konfigurera enheter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="b9a32-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="b9a32-108">Följande distributionsverktyg och -metoder stöds:</span><span class="sxs-lookup"><span data-stu-id="b9a32-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="b9a32-109">grupprincip</span><span class="sxs-lookup"><span data-stu-id="b9a32-109">group policy</span></span>
- <span data-ttu-id="b9a32-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b9a32-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="b9a32-111">Hantering av mobila enheter (inklusive Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="b9a32-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="b9a32-112">lokalt skript</span><span class="sxs-lookup"><span data-stu-id="b9a32-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b9a32-113">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="b9a32-113">In this section</span></span>
<span data-ttu-id="b9a32-114">Ämne</span><span class="sxs-lookup"><span data-stu-id="b9a32-114">Topic</span></span> | <span data-ttu-id="b9a32-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b9a32-115">Description</span></span>
:---|:---
[<span data-ttu-id="b9a32-116">Introducera Windows 10 enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="b9a32-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="b9a32-117">Använd Grupprincip för att distribuera konfigurationspaketet på enheter.</span><span class="sxs-lookup"><span data-stu-id="b9a32-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="b9a32-118">Introducera Windows enheter med hjälp av Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b9a32-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="b9a32-119">Du kan använda antingen Microsoft Endpoint Configuration Manager (current branch) version 1606 eller Microsoft Endpoint Configuration Manager (current branch) version 1602 eller tidigare för att distribuera konfigurationspaket på enheter.</span><span class="sxs-lookup"><span data-stu-id="b9a32-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="b9a32-120">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="b9a32-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="b9a32-121">Använd verktyg för hantering av mobila enheter eller Microsoft Intune till att distribuera konfigurationspaketet på enheten.</span><span class="sxs-lookup"><span data-stu-id="b9a32-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="b9a32-122">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="b9a32-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="b9a32-123">Lär dig hur du använder det lokala skriptet för att distribuera konfigurationspaketet på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="b9a32-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="b9a32-124">Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="b9a32-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="b9a32-125">Lär dig hur du använder konfigurationspaketet för att konfigurera VDI-enheter.</span><span class="sxs-lookup"><span data-stu-id="b9a32-125">Learn how to use the configuration package to configure VDI devices.</span></span>