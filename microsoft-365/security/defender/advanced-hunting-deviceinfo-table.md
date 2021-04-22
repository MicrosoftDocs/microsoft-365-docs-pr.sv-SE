---
title: DeviceInfo-tabell i det avancerade sökschemat
description: Mer information om OS, datornamn och annan maskininformation i tabellen DeviceInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e3686099606ec1cdab756bd4991cf61289299b43
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934891"
---
# <a name="deviceinfo"></a><span data-ttu-id="0cf3c-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="0cf3c-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0cf3c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0cf3c-105">**Applies to:**</span></span>
- <span data-ttu-id="0cf3c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cf3c-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="0cf3c-107">Tabellen `DeviceInfo` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om enheter i organisationen, till exempel OS-version, aktiva användare och datornamn.</span><span class="sxs-lookup"><span data-stu-id="0cf3c-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="0cf3c-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="0cf3c-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0cf3c-109">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="0cf3c-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0cf3c-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="0cf3c-110">Column name</span></span> | <span data-ttu-id="0cf3c-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0cf3c-111">Data type</span></span> | <span data-ttu-id="0cf3c-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0cf3c-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0cf3c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="0cf3c-113">datetime</span></span> | <span data-ttu-id="0cf3c-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="0cf3c-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0cf3c-115">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-115">string</span></span> | <span data-ttu-id="0cf3c-116">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="0cf3c-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0cf3c-117">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-117">string</span></span> | <span data-ttu-id="0cf3c-118">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="0cf3c-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="0cf3c-119">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-119">string</span></span> | <span data-ttu-id="0cf3c-120">Version av slutpunktsagenten eller sensorn som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="0cf3c-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="0cf3c-121">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-121">string</span></span> | <span data-ttu-id="0cf3c-122">Offentlig IP-adress som används av den onboarded machine för att ansluta till Microsoft Defender för Endpoint-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0cf3c-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="0cf3c-123">Detta kan vara IP-adressen för själva datorn, en NAT-enhet eller en proxy</span><span class="sxs-lookup"><span data-stu-id="0cf3c-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="0cf3c-124">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-124">string</span></span> | <span data-ttu-id="0cf3c-125">Arkitekturen för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="0cf3c-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="0cf3c-126">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-126">string</span></span> | <span data-ttu-id="0cf3c-127">Operativsystemets plattform som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="0cf3c-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="0cf3c-128">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7</span><span class="sxs-lookup"><span data-stu-id="0cf3c-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="0cf3c-129">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-129">string</span></span> | <span data-ttu-id="0cf3c-130">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="0cf3c-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="0cf3c-131">boolesk</span><span class="sxs-lookup"><span data-stu-id="0cf3c-131">boolean</span></span> | <span data-ttu-id="0cf3c-132">Boolesk indikator om datorn är ansluten till Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0cf3c-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="0cf3c-133">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-133">string</span></span> | <span data-ttu-id="0cf3c-134">Unikt ID för enheten i Azure AD</span><span class="sxs-lookup"><span data-stu-id="0cf3c-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="0cf3c-135">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-135">string</span></span> | <span data-ttu-id="0cf3c-136">Lista över alla användare som är inloggade på datorn vid tiden för händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="0cf3c-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="0cf3c-137">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-137">string</span></span> | <span data-ttu-id="0cf3c-138">Maskintagg som lagts till i registret</span><span class="sxs-lookup"><span data-stu-id="0cf3c-138">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="0cf3c-139">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-139">string</span></span> | <span data-ttu-id="0cf3c-140">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="0cf3c-140">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="0cf3c-141">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-141">string</span></span> | <span data-ttu-id="0cf3c-142">Datorgruppen på datorn.</span><span class="sxs-lookup"><span data-stu-id="0cf3c-142">Machine group of the machine.</span></span> <span data-ttu-id="0cf3c-143">Den här gruppen används av rollbaserad åtkomstkontroll för att avgöra åtkomsten till datorn</span><span class="sxs-lookup"><span data-stu-id="0cf3c-143">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="0cf3c-144">long</span><span class="sxs-lookup"><span data-stu-id="0cf3c-144">long</span></span> | <span data-ttu-id="0cf3c-145">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="0cf3c-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0cf3c-146">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="0cf3c-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="0cf3c-147">sträng</span><span class="sxs-lookup"><span data-stu-id="0cf3c-147">string</span></span> | <span data-ttu-id="0cf3c-148">Ytterligare information om händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="0cf3c-148">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="0cf3c-149">Tabellen `DeviceInfo` innehåller enhetsinformation baserad på hjärtslag, som är periodiska rapporter eller signaler från en enhet.</span><span class="sxs-lookup"><span data-stu-id="0cf3c-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="0cf3c-150">Var femtonde minut skickar enheten ett partiellt hjärtslag som innehåller ofta ändrar attribut som `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="0cf3c-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="0cf3c-151">En gång om dagen skickas ett fullständigt hjärtslag som innehåller enhetens attribut.</span><span class="sxs-lookup"><span data-stu-id="0cf3c-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="0cf3c-152">Du kan använda följande exempelfråga för att få den senaste statusen för en enhet:</span><span class="sxs-lookup"><span data-stu-id="0cf3c-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="0cf3c-153">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0cf3c-153">Related topics</span></span>
- [<span data-ttu-id="0cf3c-154">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="0cf3c-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0cf3c-155">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="0cf3c-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0cf3c-156">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="0cf3c-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0cf3c-157">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="0cf3c-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0cf3c-158">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="0cf3c-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0cf3c-159">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="0cf3c-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
