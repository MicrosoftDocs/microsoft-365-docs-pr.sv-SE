---
title: Funktionen AssignedIPAddresses() i avancerad sökning för Microsoft 365 Defender
description: Lär dig hur du använder funktionen AssignedIPAddresses() för att få de senaste IP-adresserna tilldelade till en enhet
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: be638141e205946be18d6a718470e7b92b18b1e7
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500413"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="7bb74-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="7bb74-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7bb74-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7bb74-105">**Applies to:**</span></span>
- <span data-ttu-id="7bb74-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bb74-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7bb74-107">Använd funktionen `AssignedIPAddresses()` för avancerade [sökfrågor för](advanced-hunting-overview.md) att snabbt hämta de senaste IP-adresserna som har tilldelats till en enhet.</span><span class="sxs-lookup"><span data-stu-id="7bb74-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="7bb74-108">Om du anger ett tidsstämpelargument hämtar den här funktionen de senaste IP-adresserna vid den angivna tiden.</span><span class="sxs-lookup"><span data-stu-id="7bb74-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="7bb74-109">Den här funktionen returnerar en tabell med följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="7bb74-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="7bb74-110">Kolumn</span><span class="sxs-lookup"><span data-stu-id="7bb74-110">Column</span></span> | <span data-ttu-id="7bb74-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="7bb74-111">Data type</span></span> | <span data-ttu-id="7bb74-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7bb74-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="7bb74-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7bb74-113">datetime</span></span> | <span data-ttu-id="7bb74-114">Senaste gången då enheten observerades med HJÄLP av IP-adressen</span><span class="sxs-lookup"><span data-stu-id="7bb74-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="7bb74-115">sträng</span><span class="sxs-lookup"><span data-stu-id="7bb74-115">string</span></span> | <span data-ttu-id="7bb74-116">IP-adress som används av enheten</span><span class="sxs-lookup"><span data-stu-id="7bb74-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="7bb74-117">sträng</span><span class="sxs-lookup"><span data-stu-id="7bb74-117">string</span></span> | <span data-ttu-id="7bb74-118">Anger om IP-adressen är en offentlig eller privat adress</span><span class="sxs-lookup"><span data-stu-id="7bb74-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="7bb74-119">int</span><span class="sxs-lookup"><span data-stu-id="7bb74-119">int</span></span> | <span data-ttu-id="7bb74-120">Nätverksadaptertyp som används av enheten som har tilldelats IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="7bb74-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="7bb74-121">Information om möjliga värden finns i [denna uppräkning](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="7bb74-121">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="7bb74-122">int</span><span class="sxs-lookup"><span data-stu-id="7bb74-122">int</span></span> | <span data-ttu-id="7bb74-123">Nätverk som adaptern med den tilldelade IP-adressen är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="7bb74-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="7bb74-124">Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet</span><span class="sxs-lookup"><span data-stu-id="7bb74-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="7bb74-125">Syntax</span><span class="sxs-lookup"><span data-stu-id="7bb74-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="7bb74-126">Argument</span><span class="sxs-lookup"><span data-stu-id="7bb74-126">Arguments</span></span>

- <span data-ttu-id="7bb74-127">**x**– `DeviceId` eller värde som identifierar `DeviceName` enheten</span><span class="sxs-lookup"><span data-stu-id="7bb74-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="7bb74-128">**y**– (datetime)-värde som instruerar funktionen för att hämta de senast tilldelade `Timestamp` IP-adresserna från en viss tid.</span><span class="sxs-lookup"><span data-stu-id="7bb74-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="7bb74-129">Om detta inte anges returnerar funktionen de senaste IP-adresserna.</span><span class="sxs-lookup"><span data-stu-id="7bb74-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="7bb74-130">Exempel</span><span class="sxs-lookup"><span data-stu-id="7bb74-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="7bb74-131">Hämta listan med IP-adresser som användes av en enhet för 24 timmar sedan</span><span class="sxs-lookup"><span data-stu-id="7bb74-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="7bb74-132">Få IP-adresser använda av en enhet och hitta enheter som kommunicerar med den</span><span class="sxs-lookup"><span data-stu-id="7bb74-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="7bb74-133">Den här frågan använder `AssignedIPAddresses()` funktionen för att hämta tilldelade IP-adresser för enheten `example-device-name` () på eller före ett visst datum ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="7bb74-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="7bb74-134">Därefter används IP-adresserna för att hitta anslutningar till enheten initierad av andra enheter.</span><span class="sxs-lookup"><span data-stu-id="7bb74-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a><span data-ttu-id="7bb74-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7bb74-135">Related topics</span></span>
- [<span data-ttu-id="7bb74-136">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="7bb74-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7bb74-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="7bb74-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7bb74-138">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="7bb74-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)