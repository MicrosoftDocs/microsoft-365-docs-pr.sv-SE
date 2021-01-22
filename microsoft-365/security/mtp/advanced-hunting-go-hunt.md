---
title: Få relevant information om en entitet med go-leta
description: Lär dig hur du använder sökverktyget för att snabbt söka efter relevant information om en enhet eller händelse med avancerad sökning.
keywords: avancerad sökning, incident, pivot, entitet, sök, relevanta händelser, hotsökning, sökning, fråga, telemetri, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929517"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="2c661-104">Snabbt jaga efter entitets- eller händelseinformation med go-jagning</span><span class="sxs-lookup"><span data-stu-id="2c661-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2c661-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2c661-105">**Applies to:**</span></span>
- <span data-ttu-id="2c661-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c661-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2c661-107">Med *sökåtgärden* Go kan du snabbt undersöka händelser och olika enhetstyper med hjälp av kraftfulla [frågebaserade avancerade](advanced-hunting-overview.md) sökfunktioner.</span><span class="sxs-lookup"><span data-stu-id="2c661-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="2c661-108">Den här åtgärden kör automatiskt en avancerad sökningsfråga för att hitta relevant information om den valda händelsen eller enheten.</span><span class="sxs-lookup"><span data-stu-id="2c661-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="2c661-109">Åtgärden *gå-och-leta* är tillgänglig i olika delar av säkerhetscentret när händelse- eller entitetsinformation visas.</span><span class="sxs-lookup"><span data-stu-id="2c661-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="2c661-110">Du kan till exempel använda *gå-jaga* från följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2c661-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="2c661-111">På [incidentsidan kan](investigate-incidents.md#incident-overview)du granska information om användare, enheter och många andra enheter som är kopplade till en incident.</span><span class="sxs-lookup"><span data-stu-id="2c661-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="2c661-112">När du väljer en enhet får du ytterligare information samt olika åtgärder du kan utföra på den personen.</span><span class="sxs-lookup"><span data-stu-id="2c661-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="2c661-113">I exemplet nedan är en postlåda markerad och visar information om postlådan samt alternativet att leta efter mer information om postlådan.</span><span class="sxs-lookup"><span data-stu-id="2c661-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Bild som visar information om postlådan med alternativet gå-och-leta](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="2c661-115">På incidentsidan kan du också komma åt en lista med enheter under bevisfliken. Om du väljer en av dessa enheter kan du snabbt jaga information om enheten.</span><span class="sxs-lookup"><span data-stu-id="2c661-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Bild som visar vald fil med sökalternativet Gå på fliken Bevis](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="2c661-117">När du visar tidslinjen för en enhet kan du välja en händelse på tidslinjen för att visa ytterligare information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="2c661-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="2c661-118">När en händelse har valts får du möjlighet att jaga andra relevanta händelser i avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="2c661-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Bild som visar händelseinformation med alternativet gå-och-leta](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="2c661-120">Om **du väljer** **Söksök eller Sök efter relaterade** händelser passeras olika frågor, beroende på om du har valt en enhet eller en händelse.</span><span class="sxs-lookup"><span data-stu-id="2c661-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="2c661-121">Fråga för entitetsinformation</span><span class="sxs-lookup"><span data-stu-id="2c661-121">Query for entity information</span></span>
<span data-ttu-id="2c661-122">När du *använder sökfråga* efter information om en användare, enhet eller någon annan typ av entitet genomsöks alla relevanta schematabeller efter händelser som innefattar den enheten.</span><span class="sxs-lookup"><span data-stu-id="2c661-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="2c661-123">För att resultatet ska kunna hanteras begränsades frågan till ungefär samma tidsperiod som den tidigaste aktiviteten under de senaste 30 dagarna som innefattar enheten och som är associerad med händelsen.</span><span class="sxs-lookup"><span data-stu-id="2c661-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="2c661-124">Här är ett exempel på sökfrågan för en enhet:</span><span class="sxs-lookup"><span data-stu-id="2c661-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="2c661-125">Entitetstyper som stöds</span><span class="sxs-lookup"><span data-stu-id="2c661-125">Supported entity types</span></span>
<span data-ttu-id="2c661-126">Du kan använda *gåsök när* du har valt någon av dessa entitetstyper:</span><span class="sxs-lookup"><span data-stu-id="2c661-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="2c661-127">Filer</span><span class="sxs-lookup"><span data-stu-id="2c661-127">Files</span></span>
- <span data-ttu-id="2c661-128">E-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="2c661-128">Emails</span></span>
- <span data-ttu-id="2c661-129">E-postkluster</span><span class="sxs-lookup"><span data-stu-id="2c661-129">Email clusters</span></span>
- <span data-ttu-id="2c661-130">Postlådor</span><span class="sxs-lookup"><span data-stu-id="2c661-130">Mailboxes</span></span>
- <span data-ttu-id="2c661-131">Användare</span><span class="sxs-lookup"><span data-stu-id="2c661-131">Users</span></span>
- <span data-ttu-id="2c661-132">Enheter</span><span class="sxs-lookup"><span data-stu-id="2c661-132">Devices</span></span>
- <span data-ttu-id="2c661-133">IP-adresser</span><span class="sxs-lookup"><span data-stu-id="2c661-133">IP addresses</span></span>
- <span data-ttu-id="2c661-134">URL:er</span><span class="sxs-lookup"><span data-stu-id="2c661-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="2c661-135">Fråga för händelseinformation</span><span class="sxs-lookup"><span data-stu-id="2c661-135">Query for event information</span></span>
<span data-ttu-id="2c661-136">När du *använder sökfråga* efter information om en tidslinjehändelse söker frågan igenom alla relevanta schematabeller efter andra händelser vid den valda händelsens tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="2c661-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="2c661-137">I följande fråga visas till exempel händelser i olika schematabeller som inträffade under samma tidsperiod på samma enhet:</span><span class="sxs-lookup"><span data-stu-id="2c661-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="2c661-138">Justera frågan</span><span class="sxs-lookup"><span data-stu-id="2c661-138">Adjust the query</span></span>
<span data-ttu-id="2c661-139">Om du har viss kunskap [om frågespråket](advanced-hunting-query-language.md)kan du justera frågan efter dina önskemål.</span><span class="sxs-lookup"><span data-stu-id="2c661-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="2c661-140">Du kan till exempel justera den här raden, som bestämmer storleken på ett tidsfönster:</span><span class="sxs-lookup"><span data-stu-id="2c661-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="2c661-141">Förutom att ändra frågan för att få mer relevanta resultat kan du också:</span><span class="sxs-lookup"><span data-stu-id="2c661-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="2c661-142">Visa resultatet som diagram</span><span class="sxs-lookup"><span data-stu-id="2c661-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="2c661-143">Skapa en anpassad identifieringsregel</span><span class="sxs-lookup"><span data-stu-id="2c661-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="2c661-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2c661-144">Related topics</span></span>
- [<span data-ttu-id="2c661-145">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="2c661-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2c661-146">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="2c661-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2c661-147">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="2c661-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="2c661-148">Anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="2c661-148">Custom detection rules</span></span>](custom-detection-rules.md)
