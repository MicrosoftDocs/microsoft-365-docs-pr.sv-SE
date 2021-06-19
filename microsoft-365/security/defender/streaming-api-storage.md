---
title: Strömma Microsoft 365 Defender händelser till ditt Storage konto
description: Läs om hur du Microsoft 365 Defender att strömma Advanced Hunting-händelser till ditt Storage konto.
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029663"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Konfigurera Microsoft 365 Defender att strömma Advanced Hunting-händelser till ditt Storage konto

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Innan du börjar

1. Skapa ett [Storage konto](/azure/storage/common/storage-account-overview) i klientorganisationen.

2. Logga in på [din Azure-klientorganisation](https://ms.portal.azure.com/)och gå till Prenumerationer > Din > eller **resursleverantörer > Registrera dig på Microsoft.Insights.**

## <a name="enable-raw-data-streaming"></a>Aktivera direktuppspelning av rådata

1. Logga in på Microsoft 365 Defender <https://security.microsoft.com> () som en ***global administratör** _ eller _*_säkerhetsadministratör_**.

2. Gå till **Inställningar** \> **Microsoft 365 Defender** \> **Streaming API**. Om du vill gå direkt till **sidan Streaming API** använder du <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .

3. Klicka på **Lägg till**.

4. I den **utfällande menyn Lägg** till nya inställningar för Streaming API konfigurerar du följande inställningar:
   1. **Namn**: Välj ett namn för de nya inställningarna.
   2. Välj **Vidarebefordra händelser om du vill Azure-lagring**.
   3. I rutan **Storage Kontoresurs-ID** som visas anger du Storage **Kontoresurs-ID**. Om du vill **Storage** kontoresurs-ID öppnar du Azure-portalen hos , klickar Storage konton går till fliken Egenskaper och kopierar <https://portal.azure.com> texten under Storage  \> \> **Kontoresurs-ID**.

      ![Bild av händelsehubbresurs-ID1](../defender-endpoint/images/storage-account-resource-id.png)

   4. När du är tillbaka **på den utfällande menyn** Lägg till nya inställningar för Streaming API väljer du de händelsetyper du vill strömma. 

   När du är klar klickar du på **Skicka.**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Schemat för händelserna i Storage konto

- En blob-behållare skapas för varje händelsetyp:

  ![Bild av händelsehubbresurs-ID2](../defender-endpoint/images/storage-account-event-schema.png)

- Schemat för varje rad i en blob är följande JSON:

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- Varje blob innehåller flera rader.

- Varje rad innehåller händelsenamnet, tiden Defender för Slutpunkt tog emot händelsen, den klientorganisation den tillhör (du får bara händelser från klientorganisationen) och händelsen i JSON-format i en egenskap som kallas "egenskaper".

- Mer information om schemat för de Microsoft 365 Defender hittar du i [Avancerad sökning – översikt.](../defender/advanced-hunting-overview.md)

## <a name="data-types-mapping"></a>Mappning av datatyper

För att hämta datatyperna för våra händelseegenskaper gör du följande:

1. Logga in på Microsoft 365 Defender ( <https://security.microsoft.com> ) och gå till **Sökning** \> **avancerad sökning.** Om du vill gå direkt till **sidan Avancerad** sökning använder du <security.microsoft.com/advanced-hunting>.

2. Kör följande **fråga** på fliken Fråga för att hämta mappningen av datatyper för varje händelse:

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Här är ett exempel för enhetsinfohändelsen:

  ![Bild av händelsehubbresurs-ID3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Avancerad sökning](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming API](streaming-api.md)
- [Strömma Microsoft 365 Defender till ditt Azure Storage-konto](streaming-api-storage.md)
- [Azure-lagring Kontodokumentation](/azure/storage/common/storage-account-overview)
