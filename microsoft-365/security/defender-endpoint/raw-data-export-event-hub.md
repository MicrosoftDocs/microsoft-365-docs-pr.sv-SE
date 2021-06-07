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
ms.custom: api
ms.openlocfilehash: 03b19f3af3c140729db2b5d51bb7ae11d906497b
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771656"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="1fd92-104">Konfigurera Microsoft Defender för Slutpunkt för att strömma Advanced Hunting-händelser till Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="1fd92-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1fd92-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1fd92-105">**Applies to:**</span></span>

- [<span data-ttu-id="1fd92-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1fd92-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="1fd92-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1fd92-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1fd92-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1fd92-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="1fd92-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="1fd92-109">Before you begin</span></span>

1. <span data-ttu-id="1fd92-110">Skapa ett [händelsenav](/azure/event-hubs/) i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="1fd92-110">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="1fd92-111">Logga in på [din Azure-klientorganisation](https://ms.portal.azure.com/)och gå till \*\*Prenumerationer > din > eller resursleverantörer > Registrera dig på \*\*Microsoft.insights\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="1fd92-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to \*\*Microsoft.insights\*\*\*\*.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="1fd92-112">Aktivera direktuppspelning av rådata</span><span class="sxs-lookup"><span data-stu-id="1fd92-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="1fd92-113">Logga in på [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com) som en \* global **administratör** _ eller _\*_säkerhetsadministratör_\*\*.</span><span class="sxs-lookup"><span data-stu-id="1fd92-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="1fd92-114">Gå till sidan [Inställningar för dataexport](https://securitycenter.windows.com/interoperability/dataexport) Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="1fd92-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="1fd92-115">Klicka på Lägg **till inställningar för dataexport.**</span><span class="sxs-lookup"><span data-stu-id="1fd92-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="1fd92-116">Välj ett namn för de nya inställningarna.</span><span class="sxs-lookup"><span data-stu-id="1fd92-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="1fd92-117">Välj **Vidarebefordra händelser till Azure Event Hubs.**</span><span class="sxs-lookup"><span data-stu-id="1fd92-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="1fd92-118">Skriv namnet **på dina händelsehubben** och **resurs-ID för Händelsehubben.**</span><span class="sxs-lookup"><span data-stu-id="1fd92-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="1fd92-119">För att hämta ditt resurs-ID för **Event Hubs** går du till din Azure Event Hubs namnområdessida på fliken egenskaper för [Azure](https://ms.portal.azure.com/) > och > kopierar texten under **Resurs-ID:**</span><span class="sxs-lookup"><span data-stu-id="1fd92-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![Bild av händelsehubbresurs-ID1](images/event-hub-resource-id.png)

7. <span data-ttu-id="1fd92-121">Välj de händelser du vill strömma och klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1fd92-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="1fd92-122">Schemat för händelserna i Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="1fd92-122">The schema of the events in Azure Event Hubs</span></span>

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

- <span data-ttu-id="1fd92-123">Varje händelsehubbmeddelande i Azure Event Hub innehåller en lista över poster.</span><span class="sxs-lookup"><span data-stu-id="1fd92-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="1fd92-124">Varje post innehåller händelsenamnet, tiden då Microsoft Defender för Slutpunkt tog emot händelsen, den klientorganisation den tillhör (du får bara händelser från klientorganisationen) och händelsen i JSON-format i en egenskap med namnet "**egenskaper**".</span><span class="sxs-lookup"><span data-stu-id="1fd92-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="1fd92-125">Mer information om schemat för Microsoft Defender för slutpunktshändelser finns i Avancerad sökning [– översikt.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1fd92-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="1fd92-126">I tabellen Avancerad sökning finns en kolumn med namnet **MachineGroup** som innehåller enhetens grupp i tabellen **DeviceInfo.**</span><span class="sxs-lookup"><span data-stu-id="1fd92-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="1fd92-127">Här är alla händelser dekorerade med den här kolumnen.</span><span class="sxs-lookup"><span data-stu-id="1fd92-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="1fd92-128">Mer information [finns i](machine-groups.md) Enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="1fd92-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="1fd92-129">Mappning av datatyper</span><span class="sxs-lookup"><span data-stu-id="1fd92-129">Data types mapping</span></span>

<span data-ttu-id="1fd92-130">Så här hämtar du datatyperna för händelseegenskaper:</span><span class="sxs-lookup"><span data-stu-id="1fd92-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="1fd92-131">Logga in på [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com) gå till [sidan Advanced Hunting.](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="1fd92-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="1fd92-132">Kör följande fråga för att hämta mappningen av datatyper för varje händelse:</span><span class="sxs-lookup"><span data-stu-id="1fd92-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="1fd92-133">Här är ett exempel för enhetsinfohändelsen:</span><span class="sxs-lookup"><span data-stu-id="1fd92-133">Here is an example for Device Info event:</span></span> 

  ![Bild av händelsenavresurs-ID2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="1fd92-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1fd92-135">Related topics</span></span>
- [<span data-ttu-id="1fd92-136">Översikt över Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="1fd92-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1fd92-137">Strömma API för Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="1fd92-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="1fd92-138">Strömma Microsoft Defender för slutpunktshändelser till ditt Azure Storage-konto</span><span class="sxs-lookup"><span data-stu-id="1fd92-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="1fd92-139">Dokumentation om Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="1fd92-139">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="1fd92-140">Felsöka anslutningsproblem – Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="1fd92-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)