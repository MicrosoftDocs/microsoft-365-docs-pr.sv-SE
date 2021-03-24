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
# <a name="raw-data-streaming-api"></a>Api för direktuppspelning av rådata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Strömma Advanced Hunting-händelser till händelsehubben och/eller Azure-lagringskontot.

Defender för Slutpunkt har stöd för direktuppspelning av alla händelser som är tillgängliga via [Avancerad](advanced-hunting-overview.md) sökning till ett [händelsenav](https://docs.microsoft.com/azure/event-hubs/) och/eller [Azure-lagringskonto.](https://docs.microsoft.com/azure/event-hubs/)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>I det här avsnittet

Ämne | Beskrivning
:---|:---
[Strömma Microsoft Defender för slutpunktshändelser till Azure Event Hubs](raw-data-export-event-hub.md)| Läs mer om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Defender för Slutpunkt för att strömma [Avancerad sökning](advanced-hunting-overview.md) till händelsehubben.
[Stream Defender för slutpunktshändelser till ditt Azure Storage-konto](raw-data-export-storage.md)| Läs om hur du aktiverar direktuppspelnings-API:t i klientorganisationen och konfigurerar Defender för Slutpunkt för att strömma [Avancerad sökning](advanced-hunting-overview.md) till ditt Azure-lagringskonto.


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Avancerad sökning](advanced-hunting-overview.md)
- [Dokumentation om Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/)
- [Dokumentation om Azure Storage Account](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
