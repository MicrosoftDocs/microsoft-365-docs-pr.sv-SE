---
title: Strömma Microsoft 365 Defender-händelser till ditt Storage konto
description: Läs om hur du konfigurerar Microsoft 365 Defender för att strömma Advanced Hunting-händelser till Storage-konto.
keywords: raw data export, streaming API, API, Event Hubs, Azure Storage, Storage Account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: a4e706bbb2246bd0629db721373ffcd4164d123d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772556"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Konfigurera Microsoft 365 Defender för att strömma Advanced Hunting-händelser till ditt Storage konto

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a>Innan du börjar:

1. Skapa ett [Storage konto](/azure/storage/common/storage-account-overview) i klientorganisationen.

2. Logga in på [din Azure-klientorganisation](https://ms.portal.azure.com/)och **gå till Prenumerationer > din > eller resursleverantörer > Registrera dig i Microsoft.Insights.**

## <a name="enable-raw-data-streaming"></a>Aktivera direktuppspelning av rådata:

1. Logga in på [Microsoft 365 Defender säkerhetscenter](https://security.microsoft.com) som en ***global administratör** _ eller _*_säkerhetsadministratör_**.

2. Gå till [sidan inställningar för dataexport](https://security.microsoft.com/settings/mtp_settings/raw_data_export) i Microsoft Defender Säkerhetscenter.

3. Klicka på Lägg **till inställningar för dataexport.**

4. Välj ett namn för de nya inställningarna.

5. Välj **Vidarebefordra händelser om du vill Azure Storage**.

6. Ange ditt **Storage Kontoresurs-ID**. För att få ditt **Storage Kontoresurs-ID** går du till din Storage-kontosida på fliken egenskaper i [Azure portal](https://ms.portal.azure.com/) > och kopierar > texten under **Storage Kontoresurs-ID:**

   ![Bild av händelsehubbresurs-ID1](../defender-endpoint/images/storage-account-resource-id.png)

7. Välj de händelser du vill strömma och klicka på **Spara**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Schemat för händelserna i det Storage kontot:

- En blob-behållare skapas för varje händelsetyp: 

  ![Bild av händelsehubbresurs-ID2](../defender-endpoint/images/storage-account-event-schema.png)

- Schemat för varje rad i en blob är följande JSON: 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- Varje blob innehåller flera rader.

- Varje rad innehåller händelsenamnet, tiden Defender för Slutpunkt tog emot händelsen, den klientorganisation den tillhör (du får bara händelser från klientorganisationen) och händelsen i JSON-format i en egenskap som kallas "egenskaper".

- Mer information om schemat för de Microsoft 365 Defender-händelser finns i Avancerad sökning [– översikt.](../defender/advanced-hunting-overview.md)


## <a name="data-types-mapping"></a>Mappning av datatyper

För att hämta datatyperna för våra händelseegenskaper gör du följande:

1. Logga in på [Microsoft 365 säkerhetscenter](https://security.microsoft.com) och gå till [sidan Advanced Hunting](https://security.microsoft.com/hunting-package).

2. Kör följande fråga för att hämta mappningen av datatyper för varje händelse: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Här är ett exempel för enhetsinfohändelsen: 

  ![Bild av händelsehubbresurs-ID3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Avancerad sökning](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming API](streaming-api.md)
- [Strömma Microsoft 365 Defender-händelser till ditt Azure Storage-konto](streaming-api-storage.md)
- [Azure Storage Kontodokumentation](/azure/storage/common/storage-account-overview)
