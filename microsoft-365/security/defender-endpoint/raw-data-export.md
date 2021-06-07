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
# <a name="raw-data-streaming-api"></a>Api för direktuppspelning av rådata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Strömma Advanced Hunting-händelser till händelsehubben och/eller Azure-lagringskontot.


Microsoft Defender för Slutpunkt har stöd för direktuppspelning av händelser som är tillgängliga [via Avancerad](../defender/advanced-hunting-overview.md) sökning till ett [händelsenav](/azure/event-hubs/) och/eller [Azure-lagringskonto.](/azure/storage/common/storage-account-overview)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>I det här avsnittet

Ämne | Beskrivning
:---|:---
[Strömma Microsoft Defender för slutpunktshändelser till Azure Event Hubs](raw-data-export-event-hub.md)| Läs mer om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Defender för Slutpunkt för att strömma [Avancerad sökning](advanced-hunting-overview.md) till händelsehubben.
[Stream Defender för slutpunktshändelser till ditt Azure Storage-konto](raw-data-export-storage.md)| Läs om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Defender för Slutpunkt för att strömma [Avancerad sökning](advanced-hunting-overview.md) till ditt Azure-lagringskonto.


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Avancerad sökning](advanced-hunting-overview.md)
- [Dokumentation om Azure Event Hubs](/azure/event-hubs/)
- [Azure Storage Kontodokumentation](/azure/storage/common/storage-account-overview)