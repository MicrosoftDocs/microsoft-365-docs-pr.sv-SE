---
title: AssignedIPAddresses ()-funktion i avancerad jakt för skydd mot Microsoft Threat
description: Lär dig hur du använder funktionen AssignedIPAddresses () för att få de senaste IP-adresserna tilldelade till en enhet
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, FileProfile, fil profil, funktion och berikning
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794237"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="9aab7-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="9aab7-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="9aab7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9aab7-105">**Applies to:**</span></span>
- <span data-ttu-id="9aab7-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="9aab7-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9aab7-107">Använd `AssignedIPAddresses()` funktionen för att snabbt få de senaste IP-adresserna som har tilldelats till en enhet eller de senaste IP-adresserna från en viss tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="9aab7-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="9aab7-108">Den här funktionen returnerar en tabell med följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="9aab7-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="9aab7-109">Kolumn</span><span class="sxs-lookup"><span data-stu-id="9aab7-109">Column</span></span> | <span data-ttu-id="9aab7-110">Datatyp</span><span class="sxs-lookup"><span data-stu-id="9aab7-110">Data type</span></span> | <span data-ttu-id="9aab7-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9aab7-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="9aab7-112">Tids</span><span class="sxs-lookup"><span data-stu-id="9aab7-112">Timestamp</span></span> | <span data-ttu-id="9aab7-113">datetime</span><span class="sxs-lookup"><span data-stu-id="9aab7-113">datetime</span></span> | <span data-ttu-id="9aab7-114">Senaste gången när enheten observerats med hjälp av IP-adressen</span><span class="sxs-lookup"><span data-stu-id="9aab7-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="9aab7-115">IP</span><span class="sxs-lookup"><span data-stu-id="9aab7-115">IPAddress</span></span> | <span data-ttu-id="9aab7-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9aab7-116">string</span></span> | <span data-ttu-id="9aab7-117">IP-adress som används av enheten</span><span class="sxs-lookup"><span data-stu-id="9aab7-117">IP address used by the device</span></span> |
| <span data-ttu-id="9aab7-118">IPType</span><span class="sxs-lookup"><span data-stu-id="9aab7-118">IPType</span></span> | <span data-ttu-id="9aab7-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9aab7-119">string</span></span> | <span data-ttu-id="9aab7-120">Anger om IP-adressen är en offentlig eller privat adress</span><span class="sxs-lookup"><span data-stu-id="9aab7-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="9aab7-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="9aab7-121">NetworkAdapterType</span></span> | <span data-ttu-id="9aab7-122">signera</span><span class="sxs-lookup"><span data-stu-id="9aab7-122">int</span></span> | <span data-ttu-id="9aab7-123">Nätverkskort typ som används av enheten som tilldelats IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="9aab7-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="9aab7-124">För möjliga värden, se [den här uppräkningen](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="9aab7-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="9aab7-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="9aab7-125">ConnectedNetworks</span></span> | <span data-ttu-id="9aab7-126">signera</span><span class="sxs-lookup"><span data-stu-id="9aab7-126">int</span></span> | <span data-ttu-id="9aab7-127">Nätverk som adaptern med den tilldelade IP-adressen är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="9aab7-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="9aab7-128">Varje JSON-matris innehåller nätverks namnet, kategorin (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet</span><span class="sxs-lookup"><span data-stu-id="9aab7-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="9aab7-129">Frågesyntaxen</span><span class="sxs-lookup"><span data-stu-id="9aab7-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="9aab7-130">Argument</span><span class="sxs-lookup"><span data-stu-id="9aab7-130">Arguments</span></span>

- <span data-ttu-id="9aab7-131">**x** – `DeviceId` eller `DeviceName` värde som identifierar enheten</span><span class="sxs-lookup"><span data-stu-id="9aab7-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="9aab7-132">**y** – `Timestamp` (datetime) värde som anger den specifika tidpunkt då de senaste IP-adresserna ska visas.</span><span class="sxs-lookup"><span data-stu-id="9aab7-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="9aab7-133">Om inget anges returnerar funktionen de senaste IP-adresserna.</span><span class="sxs-lookup"><span data-stu-id="9aab7-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="9aab7-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="9aab7-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="9aab7-135">Hämta listan med IP-adresser som används av en enhet per 24 timmar sedan</span><span class="sxs-lookup"><span data-stu-id="9aab7-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="9aab7-136">Hämta IP-adresser som används av en enhet och hitta enheter som kommunicerar med den</span><span class="sxs-lookup"><span data-stu-id="9aab7-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="9aab7-137">Den här frågan använder `AssignedIPAddresses()` funktionen för att få tilldelade IP-adresser för enheten ( `example-device-name` ) på eller före ett visst datum ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="9aab7-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="9aab7-138">Därefter används IP-adresserna för att hitta anslutningar till enheten som initieras av andra enheter.</span><span class="sxs-lookup"><span data-stu-id="9aab7-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="9aab7-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9aab7-139">Related topics</span></span>
- [<span data-ttu-id="9aab7-140">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="9aab7-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9aab7-141">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="9aab7-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9aab7-142">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="9aab7-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)