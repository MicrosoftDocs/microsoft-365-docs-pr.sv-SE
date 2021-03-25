---
title: Få relevant information om en entitet med go-leta
description: Lär dig hur du använder verktyget söksök för att snabbt söka efter relevant information om en enhet eller händelse som använder avancerad sökning.
keywords: avancerad sökning, incident, pivot, entitet, go hunt, relevanta händelser, hotsökning, sökning, sökning, fråga, telemetri, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-maave
author: martyav
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4fe3c204fe49f008cf5d9dd18b5066fa91dc6196
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075993"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="949ac-104">Snabbt jaga efter entitets- eller händelseinformation med go-hunt</span><span class="sxs-lookup"><span data-stu-id="949ac-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="949ac-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="949ac-105">**Applies to:**</span></span>
- [<span data-ttu-id="949ac-106">Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="949ac-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="949ac-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="949ac-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="949ac-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="949ac-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


<span data-ttu-id="949ac-109">Med *sökåtgärden* sök kan du snabbt undersöka händelser och olika entitetstyper med hjälp av kraftfulla [frågebaserade, avancerade](advanced-hunting-overview.md) sökfunktioner.</span><span class="sxs-lookup"><span data-stu-id="949ac-109">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="949ac-110">Den här åtgärden kör automatiskt en avancerad fråga för att hitta relevant information om den valda händelsen eller enheten.</span><span class="sxs-lookup"><span data-stu-id="949ac-110">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="949ac-111">Åtgärden *gåsök* är tillgänglig i olika delar av säkerhetscentret när händelse- eller entitetsinformation visas.</span><span class="sxs-lookup"><span data-stu-id="949ac-111">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="949ac-112">Du kan till exempel använda *gå jag* från följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="949ac-112">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="949ac-113">På [incidentsidan kan](investigate-incidents.md)du granska information om användare, enheter och många andra enheter som är kopplade till ett problem.</span><span class="sxs-lookup"><span data-stu-id="949ac-113">In the [incident page](investigate-incidents.md), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="949ac-114">När du väljer en entitet får du ytterligare information samt olika åtgärder du kan utföra på den enheten.</span><span class="sxs-lookup"><span data-stu-id="949ac-114">When you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="949ac-115">I exemplet nedan är en enhet markerad, som visar information om enheten samt alternativet för att leta efter mer information om enheten.</span><span class="sxs-lookup"><span data-stu-id="949ac-115">In the example below, a device is selected, showing details about the device as well the option to hunt for more information about the device.</span></span>

    ![Bild som visar enhetsinformation med alternativet gå-jaga](./images/go-hunt-device.png)

- <span data-ttu-id="949ac-117">På incidentsidan kan du också komma åt en lista över enheter under bevisfliken. Om du väljer en av dessa enheter kan du snabbt jaga efter information om den enheten.</span><span class="sxs-lookup"><span data-stu-id="949ac-117">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Bild som visar markerad URL med alternativet gå jaga på fliken Bevis](./images/go-hunt-evidence-url.png)

- <span data-ttu-id="949ac-119">När du visar tidslinjen för en enhet kan du välja en händelse på tidslinjen om du vill visa ytterligare information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="949ac-119">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="949ac-120">När en händelse har valts får du möjlighet att leta efter andra relevanta händelser vid avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="949ac-120">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Bild som visar händelseinformation med alternativet gå-jaga](./images/go-hunt-event.png)

<span data-ttu-id="949ac-122">Om **du väljer Sök** efter sök eller Sök **efter** relaterade händelser passeras olika frågor, beroende på om du har valt en enhet eller en händelse.</span><span class="sxs-lookup"><span data-stu-id="949ac-122">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="949ac-123">Fråga för entitetsinformation</span><span class="sxs-lookup"><span data-stu-id="949ac-123">Query for entity information</span></span>

<span data-ttu-id="949ac-124">När du *använder go hunt* to query för information om en användare, enhet eller någon annan typ av entitet, kontrollerar frågan alla relevanta schematabeller för alla händelser som innefattar den enheten.</span><span class="sxs-lookup"><span data-stu-id="949ac-124">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="949ac-125">För att resultatet ska kunna hanteras är frågan begränsad till ungefär samma tidsperiod som den tidigaste aktiviteten under de senaste 30 dagarna som innefattar enheten och som är kopplad till händelsen.</span><span class="sxs-lookup"><span data-stu-id="949ac-125">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="949ac-126">Här är ett exempel på sökfrågan för en enhet:</span><span class="sxs-lookup"><span data-stu-id="949ac-126">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```

### <a name="supported-entity-types"></a><span data-ttu-id="949ac-127">Entitetstyper som stöds</span><span class="sxs-lookup"><span data-stu-id="949ac-127">Supported entity types</span></span>

<span data-ttu-id="949ac-128">Du kan använda *gåsök när* du har valt någon av följande entitetstyper:</span><span class="sxs-lookup"><span data-stu-id="949ac-128">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="949ac-129">Filer</span><span class="sxs-lookup"><span data-stu-id="949ac-129">Files</span></span>
- <span data-ttu-id="949ac-130">Användare</span><span class="sxs-lookup"><span data-stu-id="949ac-130">Users</span></span>
- <span data-ttu-id="949ac-131">Enheter</span><span class="sxs-lookup"><span data-stu-id="949ac-131">Devices</span></span>
- <span data-ttu-id="949ac-132">IP-adresser</span><span class="sxs-lookup"><span data-stu-id="949ac-132">IP addresses</span></span>
- <span data-ttu-id="949ac-133">URL:er</span><span class="sxs-lookup"><span data-stu-id="949ac-133">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="949ac-134">Fråga för händelseinformation</span><span class="sxs-lookup"><span data-stu-id="949ac-134">Query for event information</span></span>

<span data-ttu-id="949ac-135">När du *använder sökfråga* efter information om en tidslinjehändelse söker frågan i alla relevanta schematabeller efter andra händelser vid tidpunkten för den valda händelsen.</span><span class="sxs-lookup"><span data-stu-id="949ac-135">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="949ac-136">Följande fråga visar till exempel händelser i olika schematabeller som inträffade ungefär samma tidsperiod på samma enhet:</span><span class="sxs-lookup"><span data-stu-id="949ac-136">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected RegistryValueSet event
let selectedEventTimestamp = datetime(2020-10-06T21:40:25.3466868Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "a305b52049c4658ec63ae8b55becfe5954c654a4"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="949ac-137">Justera frågan</span><span class="sxs-lookup"><span data-stu-id="949ac-137">Adjust the query</span></span>

<span data-ttu-id="949ac-138">Om du har viss kunskap [om frågespråket](advanced-hunting-query-language.md)kan du justera frågan efter dina önskemål.</span><span class="sxs-lookup"><span data-stu-id="949ac-138">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="949ac-139">Du kan till exempel justera den här raden, som bestämmer storleken på tidsfönstret:</span><span class="sxs-lookup"><span data-stu-id="949ac-139">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="949ac-140">Förutom att ändra frågan för att få mer relevanta resultat kan du också:</span><span class="sxs-lookup"><span data-stu-id="949ac-140">In addition to modifying the query to get more relevant results, you can also:</span></span>

- [<span data-ttu-id="949ac-141">Visa resultatet som diagram</span><span class="sxs-lookup"><span data-stu-id="949ac-141">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="949ac-142">Skapa en anpassad identifieringsregel</span><span class="sxs-lookup"><span data-stu-id="949ac-142">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="949ac-143">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="949ac-143">Related topics</span></span>

- [<span data-ttu-id="949ac-144">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="949ac-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="949ac-145">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="949ac-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="949ac-146">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="949ac-146">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="949ac-147">Anpassade regler för identifiering</span><span class="sxs-lookup"><span data-stu-id="949ac-147">Custom detection rules</span></span>](custom-detection-rules.md)
