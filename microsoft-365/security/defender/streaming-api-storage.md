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
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="2aded-104">Konfigurera Microsoft 365 Defender att strömma Advanced Hunting-händelser till ditt Storage konto</span><span class="sxs-lookup"><span data-stu-id="2aded-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2aded-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2aded-105">**Applies to:**</span></span>
- [<span data-ttu-id="2aded-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2aded-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="2aded-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="2aded-107">Before you begin</span></span>

1. <span data-ttu-id="2aded-108">Skapa ett [Storage konto](/azure/storage/common/storage-account-overview) i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="2aded-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="2aded-109">Logga in på [din Azure-klientorganisation](https://ms.portal.azure.com/)och gå till Prenumerationer > Din > eller **resursleverantörer > Registrera dig på Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="2aded-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="2aded-110">Aktivera direktuppspelning av rådata</span><span class="sxs-lookup"><span data-stu-id="2aded-110">Enable raw data streaming</span></span>

1. <span data-ttu-id="2aded-111">Logga in på Microsoft 365 Defender <https://security.microsoft.com> () som en ***global administratör** _ eller _*_säkerhetsadministratör_\*\*.</span><span class="sxs-lookup"><span data-stu-id="2aded-111">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="2aded-112">Gå till **Inställningar** \> **Microsoft 365 Defender** \> **Streaming API**.</span><span class="sxs-lookup"><span data-stu-id="2aded-112">Go to **Settings** \> **Microsoft 365 Defender** \> **Streaming API**.</span></span> <span data-ttu-id="2aded-113">Om du vill gå direkt till **sidan Streaming API** använder du <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .</span><span class="sxs-lookup"><span data-stu-id="2aded-113">To go directly to the **Streaming API** page, use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.</span></span>

3. <span data-ttu-id="2aded-114">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="2aded-114">Click **Add**.</span></span>

4. <span data-ttu-id="2aded-115">I den **utfällande menyn Lägg** till nya inställningar för Streaming API konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2aded-115">In the **Add new Streaming API settings** flyout that appears, configure the following settings:</span></span>
   1. <span data-ttu-id="2aded-116">**Namn**: Välj ett namn för de nya inställningarna.</span><span class="sxs-lookup"><span data-stu-id="2aded-116">**Name**: Choose a name for your new settings.</span></span>
   2. <span data-ttu-id="2aded-117">Välj **Vidarebefordra händelser om du vill Azure-lagring**.</span><span class="sxs-lookup"><span data-stu-id="2aded-117">Select **Forward events to Azure Storage**.</span></span>
   3. <span data-ttu-id="2aded-118">I rutan **Storage Kontoresurs-ID** som visas anger du Storage **Kontoresurs-ID**.</span><span class="sxs-lookup"><span data-stu-id="2aded-118">In the **Storage Account Resource ID** box that appears, type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="2aded-119">Om du vill **Storage** kontoresurs-ID öppnar du Azure-portalen hos , klickar Storage konton går till fliken Egenskaper och kopierar <https://portal.azure.com> texten under Storage  \> \> **Kontoresurs-ID**.</span><span class="sxs-lookup"><span data-stu-id="2aded-119">To get your **Storage Account Resource ID**, open the Azure portal at <https://portal.azure.com>, click **Storage accounts** \> go to the properties tab \> copy the text under **Storage Account Resource ID**.</span></span>

      ![Bild av händelsehubbresurs-ID1](../defender-endpoint/images/storage-account-resource-id.png)

   4. <span data-ttu-id="2aded-121">När du är tillbaka **på den utfällande menyn** Lägg till nya inställningar för Streaming API väljer du de händelsetyper du vill strömma. </span><span class="sxs-lookup"><span data-stu-id="2aded-121">Back on the **Add new Streaming API settings** flyout, choose the **Event types** that you want to stream.</span></span>

   <span data-ttu-id="2aded-122">När du är klar klickar du på **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="2aded-122">When you're finished, click **Submit**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="2aded-123">Schemat för händelserna i Storage konto</span><span class="sxs-lookup"><span data-stu-id="2aded-123">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="2aded-124">En blob-behållare skapas för varje händelsetyp:</span><span class="sxs-lookup"><span data-stu-id="2aded-124">A blob container will be created for each event type:</span></span>

  ![Bild av händelsehubbresurs-ID2](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="2aded-126">Schemat för varje rad i en blob är följande JSON:</span><span class="sxs-lookup"><span data-stu-id="2aded-126">The schema of each row in a blob is the following JSON:</span></span>

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- <span data-ttu-id="2aded-127">Varje blob innehåller flera rader.</span><span class="sxs-lookup"><span data-stu-id="2aded-127">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="2aded-128">Varje rad innehåller händelsenamnet, tiden Defender för Slutpunkt tog emot händelsen, den klientorganisation den tillhör (du får bara händelser från klientorganisationen) och händelsen i JSON-format i en egenskap som kallas "egenskaper".</span><span class="sxs-lookup"><span data-stu-id="2aded-128">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="2aded-129">Mer information om schemat för de Microsoft 365 Defender hittar du i [Avancerad sökning – översikt.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2aded-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="2aded-130">Mappning av datatyper</span><span class="sxs-lookup"><span data-stu-id="2aded-130">Data types mapping</span></span>

<span data-ttu-id="2aded-131">För att hämta datatyperna för våra händelseegenskaper gör du följande:</span><span class="sxs-lookup"><span data-stu-id="2aded-131">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="2aded-132">Logga in på Microsoft 365 Defender ( <https://security.microsoft.com> ) och gå till **Sökning** \> **avancerad sökning.**</span><span class="sxs-lookup"><span data-stu-id="2aded-132">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Hunting** \> **Advanced hunting**.</span></span> <span data-ttu-id="2aded-133">Om du vill gå direkt till **sidan Avancerad** sökning använder du <security.microsoft.com/advanced-hunting>.</span><span class="sxs-lookup"><span data-stu-id="2aded-133">To go directly to the **Advanced hunting** page, use <security.microsoft.com/advanced-hunting>.</span></span>

2. <span data-ttu-id="2aded-134">Kör följande **fråga** på fliken Fråga för att hämta mappningen av datatyper för varje händelse:</span><span class="sxs-lookup"><span data-stu-id="2aded-134">On the **Query** tab, run the following query to get the data types mapping for each event:</span></span>

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- <span data-ttu-id="2aded-135">Här är ett exempel för enhetsinfohändelsen:</span><span class="sxs-lookup"><span data-stu-id="2aded-135">Here is an example for Device Info event:</span></span>

  ![Bild av händelsehubbresurs-ID3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="2aded-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2aded-137">Related topics</span></span>

- [<span data-ttu-id="2aded-138">Översikt över Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="2aded-138">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="2aded-139">Microsoft 365 Defender Streaming API</span><span class="sxs-lookup"><span data-stu-id="2aded-139">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="2aded-140">Strömma Microsoft 365 Defender till ditt Azure Storage-konto</span><span class="sxs-lookup"><span data-stu-id="2aded-140">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="2aded-141">Azure-lagring Kontodokumentation</span><span class="sxs-lookup"><span data-stu-id="2aded-141">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
