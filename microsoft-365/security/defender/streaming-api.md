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
ms.openlocfilehash: 21a83c4876a90a231eb2a78d10a290be2dca2fa0
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782493"
---
# <a name="streaming-api"></a><span data-ttu-id="312fd-104">Streaming API</span><span class="sxs-lookup"><span data-stu-id="312fd-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="312fd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="312fd-105">**Applies to:**</span></span>
- [<span data-ttu-id="312fd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="312fd-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="312fd-107">Strömma Advanced Hunting-händelser till händelsehubben och/eller Azure-lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="312fd-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="312fd-108">Microsoft 365 Defender stöder direktuppspelning av händelser [via Advanced Hunting](../defender/advanced-hunting-overview.md) till ett händelsenav och/eller [Azure-lagringskonto.](/azure/event-hubs/) [](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="312fd-108">Microsoft 365 Defender supports streaming events through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="312fd-109">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="312fd-109">In this section</span></span>

<span data-ttu-id="312fd-110">Ämne</span><span class="sxs-lookup"><span data-stu-id="312fd-110">Topic</span></span> | <span data-ttu-id="312fd-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="312fd-111">Description</span></span>
:---|:---
[<span data-ttu-id="312fd-112">Strömma händelser till Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="312fd-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="312fd-113">Läs mer om hur du aktiverar api:t för direktuppspelning i klientorganisationen och konfigurerar Microsoft 365 Defender för att strömma [Advanced Hunting](../defender/advanced-hunting-overview.md) till Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="312fd-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="312fd-114">Strömma händelser till ditt Azure Storage-konto</span><span class="sxs-lookup"><span data-stu-id="312fd-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="312fd-115">Läs om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Microsoft 365 Defender för att strömma [Avancerad sökning](advanced-hunting-overview.md) till ditt Azure-lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="312fd-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="312fd-116">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="312fd-116">Related topics</span></span>
- [<span data-ttu-id="312fd-117">Översikt över Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="312fd-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="312fd-118">Dokumentation om Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="312fd-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="312fd-119">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="312fd-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
