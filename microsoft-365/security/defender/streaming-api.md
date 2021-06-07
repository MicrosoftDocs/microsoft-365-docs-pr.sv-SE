---
title: Streama Microsoft 365 Defender-händelser
description: Läs om hur du konfigurerar Microsoft 365 Defender för att strömma Advanced Hunting-händelser till händelsehubben eller Azure-lagringskontot
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
ms.openlocfilehash: fad3dd64c9acf079bd8da778d417240c44031569
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772536"
---
# <a name="streaming-api"></a><span data-ttu-id="fdeab-104">Streaming API</span><span class="sxs-lookup"><span data-stu-id="fdeab-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fdeab-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fdeab-105">**Applies to:**</span></span>
- [<span data-ttu-id="fdeab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fdeab-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="fdeab-107">Strömma Advanced Hunting-händelser till händelsehubben och/eller Azure-lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="fdeab-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="fdeab-108">Microsoft 365 Defender stöder direktuppspelning av alla händelser som är tillgängliga [via Avancerad sökning](../defender/advanced-hunting-overview.md) till ett [evenemangsnav](/azure/event-hubs/) och/eller [Azure-lagringskonto.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="fdeab-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="fdeab-109">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="fdeab-109">In this section</span></span>

<span data-ttu-id="fdeab-110">Ämne</span><span class="sxs-lookup"><span data-stu-id="fdeab-110">Topic</span></span> | <span data-ttu-id="fdeab-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fdeab-111">Description</span></span>
:---|:---
[<span data-ttu-id="fdeab-112">Strömma händelser till Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="fdeab-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="fdeab-113">Läs mer om hur du aktiverar api:t för direktuppspelning i klientorganisationen och konfigurerar Microsoft 365 Defender för att strömma [Advanced Hunting](../defender/advanced-hunting-overview.md) till Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="fdeab-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="fdeab-114">Strömma händelser till ditt Azure Storage-konto</span><span class="sxs-lookup"><span data-stu-id="fdeab-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="fdeab-115">Läs om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Microsoft 365 Defender för att strömma [Avancerad sökning](advanced-hunting-overview.md) till ditt Azure-lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="fdeab-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="fdeab-116">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fdeab-116">Related topics</span></span>
- [<span data-ttu-id="fdeab-117">Översikt över Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="fdeab-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="fdeab-118">Dokumentation om Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="fdeab-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="fdeab-119">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="fdeab-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
