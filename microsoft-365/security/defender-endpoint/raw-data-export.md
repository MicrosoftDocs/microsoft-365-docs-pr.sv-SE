---
title: Streama Microsoft Defender för Endpoint-händelse
description: Lär dig hur du konfigurerar Microsoft Defender för Slutpunkt för att strömma Advanced Hunting-händelser till händelsehubben eller Azure-lagringskontot
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
ms.custom: api
ms.openlocfilehash: c8403dee11070dcf0825fad2502d8d21d54933fd
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782759"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="f6983-104">Api för direktuppspelning av rådata</span><span class="sxs-lookup"><span data-stu-id="f6983-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6983-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f6983-105">**Applies to:**</span></span>
- [<span data-ttu-id="f6983-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f6983-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="f6983-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f6983-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f6983-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f6983-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="f6983-109">Strömma Advanced Hunting-händelser till händelsehubben och/eller Azure-lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="f6983-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>


<span data-ttu-id="f6983-110">Microsoft Defender för Slutpunkt har stöd för direktuppspelning av händelser som är tillgängliga [via Avancerad](../defender/advanced-hunting-overview.md) sökning till ett [händelsenav](/azure/event-hubs/) och/eller [Azure-lagringskonto.](/azure/storage/common/storage-account-overview)</span><span class="sxs-lookup"><span data-stu-id="f6983-110">Microsoft Defender for Endpoint supports streaming events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/storage/common/storage-account-overview).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="f6983-111">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="f6983-111">In this section</span></span>

<span data-ttu-id="f6983-112">Ämne</span><span class="sxs-lookup"><span data-stu-id="f6983-112">Topic</span></span> | <span data-ttu-id="f6983-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f6983-113">Description</span></span>
:---|:---
[<span data-ttu-id="f6983-114">Strömma Microsoft Defender för slutpunktshändelser till Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="f6983-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="f6983-115">Läs mer om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Defender för Slutpunkt för att strömma [Avancerad sökning](advanced-hunting-overview.md) till händelsehubben.</span><span class="sxs-lookup"><span data-stu-id="f6983-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="f6983-116">Stream Defender för slutpunktshändelser till ditt Azure Storage-konto</span><span class="sxs-lookup"><span data-stu-id="f6983-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="f6983-117">Läs om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Defender för Slutpunkt för att strömma [Avancerad sökning](advanced-hunting-overview.md) till ditt Azure-lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="f6983-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f6983-118">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f6983-118">Related topics</span></span>
- [<span data-ttu-id="f6983-119">Översikt över Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="f6983-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f6983-120">Dokumentation om Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="f6983-120">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="f6983-121">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="f6983-121">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)