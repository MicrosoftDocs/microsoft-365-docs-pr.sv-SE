---
title: Strömma Microsoft Defender för slutpunktshändelser till ditt lagringskonto
description: Läs om hur du konfigurerar Microsoft Defender för Slutpunkt för att strömma Advanced Hunting-händelser till ditt lagringskonto.
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
ms.openlocfilehash: 19fe0c9c3dc6f2e4226a4aa9a6cd983bc95bae3a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688795"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="9503d-104">Konfigurera Microsoft Defender för slutpunkt för att strömma Advanced Hunting-händelser till ditt lagringskonto</span><span class="sxs-lookup"><span data-stu-id="9503d-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9503d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9503d-105">**Applies to:**</span></span>
- [<span data-ttu-id="9503d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9503d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="9503d-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="9503d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9503d-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="9503d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="9503d-109">Innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="9503d-109">Before you begin:</span></span>

1. <span data-ttu-id="9503d-110">Skapa ett [lagringskonto](https://docs.microsoft.com/azure/storage/common/storage-account-overview) i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="9503d-110">Create a [Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="9503d-111">Logga in på [din Azure-klientorganisation](https://ms.portal.azure.com/)och gå **till Prenumerationer > din > eller resursleverantörer > Registrera dig på Microsoft.insights.**</span><span class="sxs-lookup"><span data-stu-id="9503d-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="9503d-112">Aktivera direktuppspelning av rådata:</span><span class="sxs-lookup"><span data-stu-id="9503d-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="9503d-113">Logga in i [Microsoft Defender för Endpoint-portalen](https://securitycenter.windows.com) som en ***global administratör** _ eller _*_säkerhetsadministratör_\*\*.</span><span class="sxs-lookup"><span data-stu-id="9503d-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="9503d-114">Gå till [sidan Inställningar för dataexport](https://securitycenter.windows.com/interoperability/dataexport) i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="9503d-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="9503d-115">Klicka på Lägg **till inställningar för dataexport.**</span><span class="sxs-lookup"><span data-stu-id="9503d-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="9503d-116">Välj ett namn för de nya inställningarna.</span><span class="sxs-lookup"><span data-stu-id="9503d-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="9503d-117">Välj **Vidarebefordra händelser till Azure Storage.**</span><span class="sxs-lookup"><span data-stu-id="9503d-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="9503d-118">Ange ditt **resurs-ID för lagringskonto.**</span><span class="sxs-lookup"><span data-stu-id="9503d-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="9503d-119">För att få ditt **resurs-ID** för lagringskonto går du till sidan Lagringskonto på fliken Egenskaper > [i Azure Portal](https://ms.portal.azure.com/) > kopiera texten under **Resurs-ID för lagringskonto:**</span><span class="sxs-lookup"><span data-stu-id="9503d-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![Bild av händelsehubbresurs-ID1](images/storage-account-resource-id.png)

7. <span data-ttu-id="9503d-121">Välj de händelser du vill strömma och klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9503d-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="9503d-122">Schemat för händelserna i lagringskontot:</span><span class="sxs-lookup"><span data-stu-id="9503d-122">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="9503d-123">En blob-behållare skapas för varje händelsetyp:</span><span class="sxs-lookup"><span data-stu-id="9503d-123">A blob container will be created for each event type:</span></span> 

  ![Bild av händelsehubbresurs-ID2](images/storage-account-event-schema.png)

- <span data-ttu-id="9503d-125">Schemat för varje rad i en blob är följande JSON:</span><span class="sxs-lookup"><span data-stu-id="9503d-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="9503d-126">Varje blob innehåller flera rader.</span><span class="sxs-lookup"><span data-stu-id="9503d-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="9503d-127">Varje rad innehåller händelsenamnet, tiden Defender för Slutpunkt tog emot händelsen, den klientorganisation den tillhör (du får bara händelser från klientorganisationen) och händelsen i JSON-format i en egenskap som kallas "egenskaper".</span><span class="sxs-lookup"><span data-stu-id="9503d-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="9503d-128">Mer information om schemat för Microsoft Defender för slutpunktshändelser finns i Avancerad sökning [– översikt.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9503d-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="9503d-129">I tabellen Avancerad sökning finns en kolumn med namnet **MachineGroup** som innehåller enhetens grupp i tabellen **DeviceInfo.**</span><span class="sxs-lookup"><span data-stu-id="9503d-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="9503d-130">Här är alla händelser dekorerade med den här kolumnen.</span><span class="sxs-lookup"><span data-stu-id="9503d-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="9503d-131">Mer information [finns i](machine-groups.md) Enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="9503d-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="9503d-132">Mappning av datatyper:</span><span class="sxs-lookup"><span data-stu-id="9503d-132">Data types mapping:</span></span>

<span data-ttu-id="9503d-133">För att hämta datatyperna för våra händelseegenskaper gör du följande:</span><span class="sxs-lookup"><span data-stu-id="9503d-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="9503d-134">Logga in på [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com) och gå till [sidan Advanced Hunting.](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="9503d-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="9503d-135">Kör följande fråga för att hämta mappningen av datatyper för varje händelse:</span><span class="sxs-lookup"><span data-stu-id="9503d-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="9503d-136">Här är ett exempel för enhetsinfohändelsen:</span><span class="sxs-lookup"><span data-stu-id="9503d-136">Here is an example for Device Info event:</span></span> 

  ![Bild av händelsehubbresurs-ID3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="9503d-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9503d-138">Related topics</span></span>
- [<span data-ttu-id="9503d-139">Översikt över Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="9503d-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9503d-140">Microsoft Defender för slutpunkts-API för direktuppspelning</span><span class="sxs-lookup"><span data-stu-id="9503d-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="9503d-141">Strömma Microsoft Defender för slutpunktshändelser till ditt Azure Storage-konto</span><span class="sxs-lookup"><span data-stu-id="9503d-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="9503d-142">Dokumentation om Azure Storage Account</span><span class="sxs-lookup"><span data-stu-id="9503d-142">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
