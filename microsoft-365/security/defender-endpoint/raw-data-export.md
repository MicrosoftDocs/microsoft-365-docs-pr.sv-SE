---
title: Streama Microsoft Defender för Endpoint-händelse
description: Lär dig hur du konfigurerar Microsoft Defender ATP för att strömma Advanced Hunting-händelser till händelsehubben eller Azure-lagringskontot
keywords: raw data export, streaming API, API, Event hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071882"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="e754e-104">Api för direktuppspelning av rådata</span><span class="sxs-lookup"><span data-stu-id="e754e-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e754e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e754e-105">**Applies to:**</span></span>
- [<span data-ttu-id="e754e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e754e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="e754e-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e754e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e754e-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e754e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="e754e-109">Strömma Advanced Hunting-händelser till händelsehubben och/eller Azure-lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="e754e-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="e754e-110">Defender för Slutpunkt har stöd för direktuppspelning av alla händelser som är tillgängliga via [Avancerad](advanced-hunting-overview.md) sökning till ett [händelsenav](https://docs.microsoft.com/azure/event-hubs/) och/eller [Azure-lagringskonto.](https://docs.microsoft.com/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="e754e-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) and/or [Azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="e754e-111">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="e754e-111">In this section</span></span>

<span data-ttu-id="e754e-112">Ämne</span><span class="sxs-lookup"><span data-stu-id="e754e-112">Topic</span></span> | <span data-ttu-id="e754e-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e754e-113">Description</span></span>
:---|:---
[<span data-ttu-id="e754e-114">Strömma Microsoft Defender för slutpunktshändelser till Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="e754e-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="e754e-115">Läs mer om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Defender för Slutpunkt för att strömma [Avancerad sökning](advanced-hunting-overview.md) till händelsehubben.</span><span class="sxs-lookup"><span data-stu-id="e754e-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="e754e-116">Stream Defender för slutpunktshändelser till ditt Azure Storage-konto</span><span class="sxs-lookup"><span data-stu-id="e754e-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="e754e-117">Läs om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Defender för Slutpunkt för att strömma [Avancerad sökning](advanced-hunting-overview.md) till ditt Azure-lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="e754e-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e754e-118">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e754e-118">Related topics</span></span>
- [<span data-ttu-id="e754e-119">Översikt över Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="e754e-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e754e-120">Dokumentation om Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="e754e-120">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="e754e-121">Dokumentation om Azure Storage Account</span><span class="sxs-lookup"><span data-stu-id="e754e-121">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
