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
ms.openlocfilehash: f97947c2c9f02720facae4f0c3c29ff702416261
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023135"
---
# <a name="deviceinfo"></a><span data-ttu-id="54343-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="54343-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="54343-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="54343-105">**Applies to:**</span></span>
- <span data-ttu-id="54343-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54343-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="54343-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="54343-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="54343-108">Tabellen `DeviceInfo` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om enheter i organisationen, till exempel OS-version, aktiva användare och datornamn.</span><span class="sxs-lookup"><span data-stu-id="54343-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="54343-109">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="54343-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="54343-110">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="54343-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="54343-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="54343-111">Column name</span></span> | <span data-ttu-id="54343-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="54343-112">Data type</span></span> | <span data-ttu-id="54343-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="54343-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="54343-114">datetime</span><span class="sxs-lookup"><span data-stu-id="54343-114">datetime</span></span> | <span data-ttu-id="54343-115">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="54343-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="54343-116">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-116">string</span></span> | <span data-ttu-id="54343-117">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="54343-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="54343-118">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-118">string</span></span> | <span data-ttu-id="54343-119">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="54343-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="54343-120">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-120">string</span></span> | <span data-ttu-id="54343-121">Version av slutpunktsagenten eller sensorn som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="54343-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="54343-122">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-122">string</span></span> | <span data-ttu-id="54343-123">Offentlig IP-adress som används av den onboarded machine för att ansluta till Microsoft Defender för Endpoint-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="54343-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="54343-124">Detta kan vara IP-adressen för själva datorn, en NAT-enhet eller en proxy</span><span class="sxs-lookup"><span data-stu-id="54343-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="54343-125">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-125">string</span></span> | <span data-ttu-id="54343-126">Arkitekturen för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="54343-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="54343-127">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-127">string</span></span> | <span data-ttu-id="54343-128">Operativsystemets plattform som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="54343-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="54343-129">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7</span><span class="sxs-lookup"><span data-stu-id="54343-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="54343-130">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-130">string</span></span> | <span data-ttu-id="54343-131">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="54343-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="54343-132">boolesk</span><span class="sxs-lookup"><span data-stu-id="54343-132">boolean</span></span> | <span data-ttu-id="54343-133">Boolesk indikator om datorn är ansluten till Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="54343-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="54343-134">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-134">string</span></span> | <span data-ttu-id="54343-135">Unikt ID för enheten i Azure AD</span><span class="sxs-lookup"><span data-stu-id="54343-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="54343-136">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-136">string</span></span> | <span data-ttu-id="54343-137">Lista över alla användare som är inloggade på datorn vid tiden för händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="54343-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="54343-138">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-138">string</span></span> | <span data-ttu-id="54343-139">Maskintagg som lagts till i registret</span><span class="sxs-lookup"><span data-stu-id="54343-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="54343-140">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-140">string</span></span> | <span data-ttu-id="54343-141">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="54343-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="54343-142">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-142">string</span></span> | <span data-ttu-id="54343-143">Datorgruppen på datorn.</span><span class="sxs-lookup"><span data-stu-id="54343-143">Machine group of the machine.</span></span> <span data-ttu-id="54343-144">Den här gruppen används av rollbaserad åtkomstkontroll för att avgöra åtkomsten till datorn</span><span class="sxs-lookup"><span data-stu-id="54343-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="54343-145">long</span><span class="sxs-lookup"><span data-stu-id="54343-145">long</span></span> | <span data-ttu-id="54343-146">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="54343-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="54343-147">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="54343-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="54343-148">sträng</span><span class="sxs-lookup"><span data-stu-id="54343-148">string</span></span> | <span data-ttu-id="54343-149">Ytterligare information om händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="54343-149">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="54343-150">Tabellen `DeviceInfo` innehåller enhetsinformation baserad på hjärtslag, som är periodiska rapporter eller signaler från en enhet.</span><span class="sxs-lookup"><span data-stu-id="54343-150">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="54343-151">Var femtonde minut skickar enheten ett partiellt hjärtslag som innehåller ofta ändrar attribut som `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="54343-151">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="54343-152">En gång om dagen skickas ett fullständigt hjärtslag som innehåller enhetens attribut.</span><span class="sxs-lookup"><span data-stu-id="54343-152">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="54343-153">Du kan använda följande exempelfråga för att få den senaste statusen för en enhet:</span><span class="sxs-lookup"><span data-stu-id="54343-153">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="54343-154">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="54343-154">Related topics</span></span>
- [<span data-ttu-id="54343-155">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="54343-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="54343-156">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="54343-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="54343-157">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="54343-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="54343-158">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="54343-158">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="54343-159">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="54343-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="54343-160">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="54343-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
