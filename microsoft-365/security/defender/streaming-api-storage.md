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
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="2c5c3-104">Konfigurera Microsoft 365 Defender för att strömma Advanced Hunting-händelser till ditt Storage konto</span><span class="sxs-lookup"><span data-stu-id="2c5c3-104">Configure  Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2c5c3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2c5c3-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c5c3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c5c3-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="2c5c3-107">Innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="2c5c3-107">Before you begin:</span></span>

1. <span data-ttu-id="2c5c3-108">Skapa ett [Storage konto](/azure/storage/common/storage-account-overview) i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="2c5c3-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="2c5c3-109">Logga in på [din Azure-klientorganisation](https://ms.portal.azure.com/)och **gå till Prenumerationer > din > eller resursleverantörer > Registrera dig i Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="2c5c3-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="2c5c3-110">Aktivera direktuppspelning av rådata:</span><span class="sxs-lookup"><span data-stu-id="2c5c3-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="2c5c3-111">Logga in på [Microsoft 365 Defender säkerhetscenter](https://security.microsoft.com) som en ***global administratör** _ eller _*_säkerhetsadministratör_\*\*.</span><span class="sxs-lookup"><span data-stu-id="2c5c3-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="2c5c3-112">Gå till [sidan inställningar för dataexport](https://security.microsoft.com/settings/mtp_settings/raw_data_export) i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="2c5c3-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="2c5c3-113">Klicka på Lägg **till inställningar för dataexport.**</span><span class="sxs-lookup"><span data-stu-id="2c5c3-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="2c5c3-114">Välj ett namn för de nya inställningarna.</span><span class="sxs-lookup"><span data-stu-id="2c5c3-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="2c5c3-115">Välj **Vidarebefordra händelser om du vill Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="2c5c3-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="2c5c3-116">Ange ditt **Storage Kontoresurs-ID**.</span><span class="sxs-lookup"><span data-stu-id="2c5c3-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="2c5c3-117">För att få ditt **Storage Kontoresurs-ID** går du till din Storage-kontosida på fliken egenskaper i [Azure portal](https://ms.portal.azure.com/) > och kopierar > texten under **Storage Kontoresurs-ID:**</span><span class="sxs-lookup"><span data-stu-id="2c5c3-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![Bild av händelsehubbresurs-ID1](../defender-endpoint/images/storage-account-resource-id.png)

7. <span data-ttu-id="2c5c3-119">Välj de händelser du vill strömma och klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2c5c3-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="2c5c3-120">Schemat för händelserna i det Storage kontot:</span><span class="sxs-lookup"><span data-stu-id="2c5c3-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="2c5c3-121">En blob-behållare skapas för varje händelsetyp:</span><span class="sxs-lookup"><span data-stu-id="2c5c3-121">A blob container will be created for each event type:</span></span> 

  ![Bild av händelsehubbresurs-ID2](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="2c5c3-123">Schemat för varje rad i en blob är följande JSON:</span><span class="sxs-lookup"><span data-stu-id="2c5c3-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="2c5c3-124">Varje blob innehåller flera rader.</span><span class="sxs-lookup"><span data-stu-id="2c5c3-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="2c5c3-125">Varje rad innehåller händelsenamnet, tiden Defender för Slutpunkt tog emot händelsen, den klientorganisation den tillhör (du får bara händelser från klientorganisationen) och händelsen i JSON-format i en egenskap som kallas "egenskaper".</span><span class="sxs-lookup"><span data-stu-id="2c5c3-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="2c5c3-126">Mer information om schemat för de Microsoft 365 Defender-händelser finns i Avancerad sökning [– översikt.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2c5c3-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="2c5c3-127">Mappning av datatyper</span><span class="sxs-lookup"><span data-stu-id="2c5c3-127">Data types mapping</span></span>

<span data-ttu-id="2c5c3-128">För att hämta datatyperna för våra händelseegenskaper gör du följande:</span><span class="sxs-lookup"><span data-stu-id="2c5c3-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="2c5c3-129">Logga in på [Microsoft 365 säkerhetscenter](https://security.microsoft.com) och gå till [sidan Advanced Hunting](https://security.microsoft.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="2c5c3-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="2c5c3-130">Kör följande fråga för att hämta mappningen av datatyper för varje händelse:</span><span class="sxs-lookup"><span data-stu-id="2c5c3-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="2c5c3-131">Här är ett exempel för enhetsinfohändelsen:</span><span class="sxs-lookup"><span data-stu-id="2c5c3-131">Here is an example for Device Info event:</span></span> 

  ![Bild av händelsehubbresurs-ID3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="2c5c3-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2c5c3-133">Related topics</span></span>
- [<span data-ttu-id="2c5c3-134">Översikt över Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="2c5c3-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="2c5c3-135">Microsoft 365 Defender Streaming API</span><span class="sxs-lookup"><span data-stu-id="2c5c3-135">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="2c5c3-136">Strömma Microsoft 365 Defender-händelser till ditt Azure Storage-konto</span><span class="sxs-lookup"><span data-stu-id="2c5c3-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="2c5c3-137">Azure Storage Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="2c5c3-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
