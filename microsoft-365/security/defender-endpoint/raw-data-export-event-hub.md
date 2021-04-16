---
title: Strömma Microsoft Defender för slutpunktshändelser till Azure Event Hubs
description: Läs om hur du konfigurerar Microsoft Defender för Slutpunkt för att strömma Advanced Hunting-händelser till händelsehubben.
keywords: raw data export, streaming API, API, Azure Event Hubs, Azure Storage, Storage Account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: df305c9fcc7fb9249f2387567600adb899f8c49a
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861053"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Konfigurera Microsoft Defender för Slutpunkt för att strömma Advanced Hunting-händelser till Azure Event Hub

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Innan du börjar:

1. Skapa ett [händelsenav](https://docs.microsoft.com/azure/event-hubs/) i klientorganisationen.

2. Logga in på [din Azure-klientorganisation](https://ms.portal.azure.com/)och gå till **Prenumerationer > din > eller resursleverantörer > Registrera dig på **Microsoft.insights.**

## <a name="enable-raw-data-streaming"></a>Aktivera direktuppspelning av rådata:

1. Logga in på [Microsoft Defender Säkerhetscenter som](https://securitycenter.windows.com) en * global **administratör** _ eller _*_säkerhetsadministratör_**.

2. Gå till sidan [Inställningar för dataexport](https://securitycenter.windows.com/interoperability/dataexport) i Microsoft Defender Säkerhetscenter.

3. Klicka på Lägg **till inställningar för dataexport.**

4. Välj ett namn för de nya inställningarna.

5. Välj **Vidarebefordra händelser till Azure Event Hubs.**

6. Skriv namnet **på dina händelsehubben** och **resurs-ID för Händelsehubben.**

   För att hämta ditt resurs-ID för **Event Hubs** går du till din Azure Event Hubs namnområdessida på fliken egenskaper för [Azure](https://ms.portal.azure.com/) > och > kopierar texten under **Resurs-ID:**

   ![Bild av händelsehubbresurs-ID1](images/event-hub-resource-id.png)

7. Välj de händelser du vill strömma och klicka på **Spara**.

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Schemat för händelserna i Azure Event Hub:

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Varje händelsehubbmeddelande i Azure Event Hub innehåller en lista över poster.

- Varje post innehåller händelsenamnet, tiden då Microsoft Defender för Slutpunkt tog emot händelsen, den klientorganisation den tillhör (du får bara händelser från klientorganisationen) och händelsen i JSON-format i en egenskap med namnet "**egenskaper**".

- Mer information om schemat för Microsoft Defender för slutpunktshändelser finns i Avancerad sökning [– översikt.](advanced-hunting-overview.md)

- I tabellen Avancerad sökning finns en kolumn med namnet **MachineGroup** som innehåller enhetens grupp i tabellen **DeviceInfo.** Här är alla händelser dekorerade med den här kolumnen. Mer information [finns i](machine-groups.md) Enhetsgrupper.

## <a name="data-types-mapping"></a>Mappning av datatyper:

Så här hämtar du datatyperna för händelseegenskaper:

1. Logga in på [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com) och gå till [sidan Advanced Hunting.](https://securitycenter.windows.com/hunting-package)

2. Kör följande fråga för att hämta mappningen av datatyper för varje händelse:
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Här är ett exempel för enhetsinfohändelsen: 

  ![Bild av händelsenavresurs-ID2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Avancerad sökning](advanced-hunting-overview.md)
- [Strömma API för Microsoft Defender för slutpunkt](raw-data-export.md)
- [Strömma Microsoft Defender för slutpunktshändelser till ditt Azure Storage-konto](raw-data-export-storage.md)
- [Dokumentation om Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/)
- [Felsöka anslutningsproblem – Azure Event Hub](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
