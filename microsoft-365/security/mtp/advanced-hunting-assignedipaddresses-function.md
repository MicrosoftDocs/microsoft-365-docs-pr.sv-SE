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
ms.openlocfilehash: 4ee07abe7ce1432921a843d713d0f9b914631174
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949318"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="544b9-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="544b9-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="544b9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="544b9-105">**Applies to:**</span></span>
- <span data-ttu-id="544b9-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="544b9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="544b9-107">Använd `AssignedIPAddresses()` funktionen för att snabbt få de senaste IP-adresserna som har tilldelats till en enhet.</span><span class="sxs-lookup"><span data-stu-id="544b9-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="544b9-108">Om du anger ett timestamp-argument får den här funktionen de senaste IP-adresserna vid den angivna tiden.</span><span class="sxs-lookup"><span data-stu-id="544b9-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="544b9-109">Den här funktionen returnerar en tabell med följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="544b9-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="544b9-110">Kolumn</span><span class="sxs-lookup"><span data-stu-id="544b9-110">Column</span></span> | <span data-ttu-id="544b9-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="544b9-111">Data type</span></span> | <span data-ttu-id="544b9-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="544b9-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="544b9-113">datetime</span><span class="sxs-lookup"><span data-stu-id="544b9-113">datetime</span></span> | <span data-ttu-id="544b9-114">Senaste gången när enheten observerats med hjälp av IP-adressen</span><span class="sxs-lookup"><span data-stu-id="544b9-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="544b9-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="544b9-115">string</span></span> | <span data-ttu-id="544b9-116">IP-adress som används av enheten</span><span class="sxs-lookup"><span data-stu-id="544b9-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="544b9-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="544b9-117">string</span></span> | <span data-ttu-id="544b9-118">Anger om IP-adressen är en offentlig eller privat adress</span><span class="sxs-lookup"><span data-stu-id="544b9-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="544b9-119">signera</span><span class="sxs-lookup"><span data-stu-id="544b9-119">int</span></span> | <span data-ttu-id="544b9-120">Nätverkskort typ som används av enheten som tilldelats IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="544b9-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="544b9-121">För möjliga värden, se [den här uppräkningen](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="544b9-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="544b9-122">signera</span><span class="sxs-lookup"><span data-stu-id="544b9-122">int</span></span> | <span data-ttu-id="544b9-123">Nätverk som adaptern med den tilldelade IP-adressen är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="544b9-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="544b9-124">Varje JSON-matris innehåller nätverks namnet, kategorin (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet</span><span class="sxs-lookup"><span data-stu-id="544b9-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="544b9-125">Frågesyntaxen</span><span class="sxs-lookup"><span data-stu-id="544b9-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="544b9-126">Argument</span><span class="sxs-lookup"><span data-stu-id="544b9-126">Arguments</span></span>

- <span data-ttu-id="544b9-127">**x**– `DeviceId` eller `DeviceName` värde som identifierar enheten</span><span class="sxs-lookup"><span data-stu-id="544b9-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="544b9-128">**y**– `Timestamp` (datetime)-värde som anger funktionen för att hämta de senaste tilldelade IP-adresserna från en viss tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="544b9-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="544b9-129">Om inget anges returnerar funktionen de senaste IP-adresserna.</span><span class="sxs-lookup"><span data-stu-id="544b9-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="544b9-130">Exempel</span><span class="sxs-lookup"><span data-stu-id="544b9-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="544b9-131">Hämta listan med IP-adresser som används av en enhet för mer än 24 timmar sedan</span><span class="sxs-lookup"><span data-stu-id="544b9-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="544b9-132">Hämta IP-adresser som används av en enhet och hitta enheter som kommunicerar med den</span><span class="sxs-lookup"><span data-stu-id="544b9-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="544b9-133">Den här frågan använder `AssignedIPAddresses()` funktionen för att få tilldelade IP-adresser för enheten ( `example-device-name` ) på eller före ett visst datum ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="544b9-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="544b9-134">Därefter används IP-adresserna för att hitta anslutningar till enheten som initieras av andra enheter.</span><span class="sxs-lookup"><span data-stu-id="544b9-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="544b9-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="544b9-135">Related topics</span></span>
- [<span data-ttu-id="544b9-136">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="544b9-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="544b9-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="544b9-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="544b9-138">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="544b9-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)