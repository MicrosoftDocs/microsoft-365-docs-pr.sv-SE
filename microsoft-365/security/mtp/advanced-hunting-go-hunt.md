---
title: Få relevant information om en enhet med go-letare
description: Lär dig hur du använder verktyget "go-fest" för att snabbt fråga efter relevant information om en enhet eller händelse med hjälp av avancerad jakt.
keywords: Avancerad jakt, olycka, pivot, enhet, go-evenemang, relevanta händelser, hot mot cyberterrorism hotet om sökning, frågor, telemetri, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4abbedc34b6d77e785c2096d9f334000f9ffb02f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430473"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="e056d-104">Hitta snabbt en enhet eller händelse information med go-evenemang</span><span class="sxs-lookup"><span data-stu-id="e056d-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e056d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e056d-105">**Applies to:**</span></span>
- <span data-ttu-id="e056d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e056d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e056d-107">Med åtgärden *gå* med, kan du snabbt undersöka händelser och olika entitetstyper med hjälp av kraftfulla frågor baserade på de [avancerade jakt](advanced-hunting-overview.md) funktionerna.</span><span class="sxs-lookup"><span data-stu-id="e056d-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="e056d-108">Den här åtgärden kör automatiskt en avancerad tilläggsfråga för att hitta relevant information om den markerade händelsen eller enheten.</span><span class="sxs-lookup"><span data-stu-id="e056d-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="e056d-109">Åtgärden *Go-letare* är tillgänglig i olika avsnitt i säkerhets Center när händelse-eller entitetsinformation visas.</span><span class="sxs-lookup"><span data-stu-id="e056d-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="e056d-110">Du kan till exempel använda *Go-leta* från följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="e056d-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="e056d-111">På [sidan incident](investigate-incidents.md#incident-overview)kan du granska information om användare, enheter och många andra enheter som är kopplade till en olycka.</span><span class="sxs-lookup"><span data-stu-id="e056d-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="e056d-112">När du väljer en entitet får du ytterligare information och olika åtgärder du kan vidta för den entitity.</span><span class="sxs-lookup"><span data-stu-id="e056d-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="e056d-113">I exemplet nedan är en post låda markerad, med information om post lådan och även om du väljer att ha mer information om post lådan.</span><span class="sxs-lookup"><span data-stu-id="e056d-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Bild som visar brev låde information med alternativet Sök efter](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="e056d-115">På sidan incident kan du även komma åt en lista med enheter under fliken bevis. Om du väljer någon av dessa enheter kan du snabbt hitta information om den personen.</span><span class="sxs-lookup"><span data-stu-id="e056d-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Bild som visar markerad fil med alternativet Sök efter på fliken bevis](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="e056d-117">När du visar tids linjen för en enhet kan du välja en händelse i tids linjen för att visa ytterligare information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="e056d-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="e056d-118">När en händelse är markerad får du möjlighet att hitta alla relevanta händelser i avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="e056d-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Bild som visar händelse Detaljer med alternativet Sök efter](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="e056d-120">När **Go hunt** du väljer Sök **efter relaterade händelser** skickas olika frågor, beroende på om du har valt en enhet eller en händelse.</span><span class="sxs-lookup"><span data-stu-id="e056d-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="e056d-121">Fråga efter entitetsinformation</span><span class="sxs-lookup"><span data-stu-id="e056d-121">Query for entity information</span></span>
<span data-ttu-id="e056d-122">När du använder *Go-leta* för att söka efter information om en användare, en enhet eller någon annan typ av enhet kontrollerar frågan alla relevanta schema tabeller för eventuella händelser som berör den entiteten.</span><span class="sxs-lookup"><span data-stu-id="e056d-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="e056d-123">För att resultaten ska kunna hanteras begränsas frågan till samma tids period som den tidigaste aktiviteten under de senaste 30 dagarna som berör enheten och är kopplad till händelsen.</span><span class="sxs-lookup"><span data-stu-id="e056d-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="e056d-124">Här är ett exempel på frågan Sök efter en enhet:</span><span class="sxs-lookup"><span data-stu-id="e056d-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="e056d-125">Entitetstyper som stöds</span><span class="sxs-lookup"><span data-stu-id="e056d-125">Supported entity types</span></span>
<span data-ttu-id="e056d-126">Du kan använda *gå* till efter att välja någon av följande typer av enheter:</span><span class="sxs-lookup"><span data-stu-id="e056d-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="e056d-127">Hjälpfiler</span><span class="sxs-lookup"><span data-stu-id="e056d-127">Files</span></span>
- <span data-ttu-id="e056d-128">E-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="e056d-128">Emails</span></span>
- <span data-ttu-id="e056d-129">E-postkluster</span><span class="sxs-lookup"><span data-stu-id="e056d-129">Email clusters</span></span>
- <span data-ttu-id="e056d-130">Post lådor</span><span class="sxs-lookup"><span data-stu-id="e056d-130">Mailboxes</span></span>
- <span data-ttu-id="e056d-131">Användare</span><span class="sxs-lookup"><span data-stu-id="e056d-131">Users</span></span>
- <span data-ttu-id="e056d-132">Anordningar</span><span class="sxs-lookup"><span data-stu-id="e056d-132">Devices</span></span>
- <span data-ttu-id="e056d-133">IP-adresser</span><span class="sxs-lookup"><span data-stu-id="e056d-133">IP addresses</span></span>
- <span data-ttu-id="e056d-134">Garanteras</span><span class="sxs-lookup"><span data-stu-id="e056d-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="e056d-135">Fråga efter händelse information</span><span class="sxs-lookup"><span data-stu-id="e056d-135">Query for event information</span></span>
<span data-ttu-id="e056d-136">När du använder *Go-leta* för att få information om en tids linje händelse kontrollerar frågan alla relevanta schema tabeller för andra händelser kring tiden för den markerade händelsen.</span><span class="sxs-lookup"><span data-stu-id="e056d-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="e056d-137">I följande fråga visas till exempel händelser i olika schema tabeller som har inträffat kring samma tids period på samma enhet:</span><span class="sxs-lookup"><span data-stu-id="e056d-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="e056d-138">Justera frågan</span><span class="sxs-lookup"><span data-stu-id="e056d-138">Adjust the query</span></span>
<span data-ttu-id="e056d-139">Med lite kunskap om [frågespråket](advanced-hunting-query-language.md)kan du ändra frågan till preferenser.</span><span class="sxs-lookup"><span data-stu-id="e056d-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="e056d-140">Du kan till exempel justera den här raden, som avgör tidsfönstrets storlek:</span><span class="sxs-lookup"><span data-stu-id="e056d-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="e056d-141">Förutom att ändra frågan för att få mer relevanta resultat kan du också:</span><span class="sxs-lookup"><span data-stu-id="e056d-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="e056d-142">Visa resultatet som diagram</span><span class="sxs-lookup"><span data-stu-id="e056d-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="e056d-143">Skapa en anpassad detektions regel</span><span class="sxs-lookup"><span data-stu-id="e056d-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="e056d-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e056d-144">Related topics</span></span>
- [<span data-ttu-id="e056d-145">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="e056d-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e056d-146">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="e056d-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e056d-147">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="e056d-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="e056d-148">Anpassade identifierings regler</span><span class="sxs-lookup"><span data-stu-id="e056d-148">Custom detection rules</span></span>](custom-detection-rules.md)
