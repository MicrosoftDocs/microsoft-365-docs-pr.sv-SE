---
title: Strömma Microsoft 365 Defender-händelser till Azure Event Hubs
description: Läs om hur du konfigurerar Microsoft 365 Defender för att strömma Advanced Hunting-händelser till händelsehubben.
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
ms.openlocfilehash: e2ede14d6b93a61bc232d42b5926c6adb7c9585f
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736330"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="96554-104">Konfigurera Microsoft 365 Defender för att strömma Advanced Hunting-händelser till Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="96554-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="96554-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="96554-105">**Applies to:**</span></span>
- [<span data-ttu-id="96554-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96554-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="96554-107">Innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="96554-107">Before you begin:</span></span>

1. <span data-ttu-id="96554-108">Skapa ett [händelsenav](/azure/event-hubs/) i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="96554-108">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="96554-109">Logga in på [din Azure-klientorganisation](https://ms.portal.azure.com/)och **gå till Prenumerationer > din > eller resursleverantörer > Registrera dig i Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="96554-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="96554-110">Skapa ett namnområde för  händelsehubben, gå till Händelsehubben > Lägg till och välj prissättningsnivå, dataflödesenheter och Automatiskt fylls på för förväntad belastning.</span><span class="sxs-lookup"><span data-stu-id="96554-110">Create an Event Hub Namespace, go to **Event Hubs > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="96554-111">Mer information finns i [Priser – | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="96554-111">For more information, see [Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

4. <span data-ttu-id="96554-112">När namnområdet för händelsehubben har skapats måste du lägga till programmets huvudnamn för registreringstjänsten som läsare, Azure Event Hubs Data Receiver och användaren som ska logga in på Microsoft 365 Defender som deltagare (detta kan också göras på resursgrupp- eller prenumerationsnivå).</span><span class="sxs-lookup"><span data-stu-id="96554-112">Once the event hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> <span data-ttu-id="96554-113">Gå till **namnområdet i händelsehubben > i Access-kontroll (IAM) >** Lägg till och verifiera under **Roll assignements.**</span><span class="sxs-lookup"><span data-stu-id="96554-113">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignements**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="96554-114">Aktivera direktuppspelning av rådata:</span><span class="sxs-lookup"><span data-stu-id="96554-114">Enable raw data streaming:</span></span>

1. <span data-ttu-id="96554-115">Logga in på Microsoft 365 [Defender säkerhetscenter](https://security.microsoft.com) som en ***global administratör** _ eller _*_säkerhetsadministratör_\*\*.</span><span class="sxs-lookup"><span data-stu-id="96554-115">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="96554-116">Gå till sidan [Inställningar för dataexport.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="96554-116">Go to the [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="96554-117">Klicka på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="96554-117">Click on **Add**.</span></span>

4. <span data-ttu-id="96554-118">Välj ett namn för de nya inställningarna.</span><span class="sxs-lookup"><span data-stu-id="96554-118">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="96554-119">Välj **Vidarebefordra händelser till Azure Event Hubs.**</span><span class="sxs-lookup"><span data-stu-id="96554-119">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="96554-120">Du kan välja om du vill exportera händelsedata till ett enskilt händelsenav eller exportera varje händelsetabell till ett annat även nav i namnområdet i händelsehubben.</span><span class="sxs-lookup"><span data-stu-id="96554-120">You can select if you want to export the event data to a single event hub, or to export each event table to a different even hub in your event hub namespace.</span></span> 

7. <span data-ttu-id="96554-121">Om du vill exportera händelsedata till ett enskilt händelsenav anger du namnet **på händelsehubben** och **resurs-ID för Händelsehubben.**</span><span class="sxs-lookup"><span data-stu-id="96554-121">To export the event data to a single event hub, Enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="96554-122">Om du vill **hämta ditt resurs-ID** för Händelsehubben går du till namnområdessidan i Azure-händelsehubben på fliken [Azure->](https://ms.portal.azure.com/)kopierar texten  >   under **Resurs-ID:**</span><span class="sxs-lookup"><span data-stu-id="96554-122">To get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Bild av händelsehubbresurs-ID1](images/event-hub-resource-id.png)

8. <span data-ttu-id="96554-124">Välj de händelser du vill strömma och klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="96554-124">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="96554-125">Schemat för händelserna i Azure Event Hub:</span><span class="sxs-lookup"><span data-stu-id="96554-125">The schema of the events in Azure Event Hubs:</span></span>

```
{
    "records": [
                    {
                        "time": "<The time Microsoft 365 Defender received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="96554-126">Varje händelsehubbmeddelande i Azure Event Hub innehåller en lista över poster.</span><span class="sxs-lookup"><span data-stu-id="96554-126">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="96554-127">Varje post innehåller händelsenamnet, tiden då Microsoft 365 Defender tog emot händelsen, den klientorganisation som den tillhör (du får bara händelser från klientorganisationen) och händelsen i JSON-format i en egenskap med namnet "**egenskaper**".</span><span class="sxs-lookup"><span data-stu-id="96554-127">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="96554-128">Mer information om schemat för de Microsoft 365 Defender-händelser finns i Avancerad sökning [– översikt.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="96554-128">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="96554-129">I tabellen Avancerad sökning finns en kolumn med namnet **MachineGroup** som innehåller enhetens grupp i tabellen **DeviceInfo.**</span><span class="sxs-lookup"><span data-stu-id="96554-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="96554-130">Här är alla händelser dekorerade med den här kolumnen.</span><span class="sxs-lookup"><span data-stu-id="96554-130">Here every event will be decorated with this column as well.</span></span> 

9. <span data-ttu-id="96554-131">Om du vill exportera varje händelsetabell till  ett annat händelsenav lämnar du händelsehubbens namn tomt så gör Microsoft 365 Defender resten.</span><span class="sxs-lookup"><span data-stu-id="96554-131">To export each event table to a different event hub, simply leave the **Event hub name** empty, and Microsoft 365 Defender will do the rest.</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="96554-132">Mappning av datatyper:</span><span class="sxs-lookup"><span data-stu-id="96554-132">Data types mapping:</span></span>

<span data-ttu-id="96554-133">Så här hämtar du datatyperna för händelseegenskaper:</span><span class="sxs-lookup"><span data-stu-id="96554-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="96554-134">Logga in på [Microsoft 365 säkerhetscenter](https://security.microsoft.com) och gå till [sidan Advanced Hunting](https://security.microsoft.com/hunting-package).</span><span class="sxs-lookup"><span data-stu-id="96554-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="96554-135">Kör följande fråga för att hämta mappningen av datatyper för varje händelse:</span><span class="sxs-lookup"><span data-stu-id="96554-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="96554-136">Här är ett exempel för enhetsinfohändelsen:</span><span class="sxs-lookup"><span data-stu-id="96554-136">Here is an example for Device Info event:</span></span> 

  ![Bild av händelsenavresurs-ID2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="96554-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="96554-138">Related topics</span></span>
- [<span data-ttu-id="96554-139">Översikt över Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="96554-139">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="96554-140">Microsoft 365 Defender-streaming-API</span><span class="sxs-lookup"><span data-stu-id="96554-140">Microsoft 365 Defender streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="96554-141">Strömma Microsoft 365 Defender-händelser till ditt Azure Storage-konto</span><span class="sxs-lookup"><span data-stu-id="96554-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="96554-142">Dokumentation om Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="96554-142">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="96554-143">Felsöka anslutningsproblem – Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="96554-143">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)
