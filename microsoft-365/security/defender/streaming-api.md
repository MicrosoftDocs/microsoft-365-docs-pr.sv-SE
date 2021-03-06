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
# <a name="streaming-api"></a>Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Strömma Advanced Hunting-händelser till händelsehubben och/eller Azure-lagringskontot.

Microsoft 365 Defender stöder direktuppspelning av händelser [via Advanced Hunting](../defender/advanced-hunting-overview.md) till ett händelsenav och/eller [Azure-lagringskonto.](/azure/event-hubs/) [](/azure/event-hubs/)



## <a name="in-this-section"></a>I det här avsnittet

Ämne | Beskrivning
:---|:---
[Strömma händelser till Azure Event Hubs](streaming-api-event-hub.md)| Läs mer om hur du aktiverar api:t för direktuppspelning i klientorganisationen och konfigurerar Microsoft 365 Defender för att strömma [Advanced Hunting](../defender/advanced-hunting-overview.md) till Event Hubs.
[Strömma händelser till ditt Azure Storage-konto](streaming-api-storage.md)| Läs om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Microsoft 365 Defender för att strömma [Avancerad sökning](advanced-hunting-overview.md) till ditt Azure-lagringskonto.


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Avancerad sökning](../defender/advanced-hunting-overview.md)
- [Dokumentation om Azure Event Hubs](/azure/event-hubs/)
- [Azure Storage Kontodokumentation](/azure/storage/common/storage-account-overview)
