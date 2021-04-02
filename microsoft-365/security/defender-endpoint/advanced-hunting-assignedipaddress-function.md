---
title: Funktionen AssignedIPAddresses() i avancerad sökning för Microsoft Defender för slutpunkt
description: Lär dig hur du använder funktionen AssignedIPAddresses() för att få de senaste IP-adresserna tilldelade till en enhet
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, mdatp, Microsoft Defender ATP, Microsoft Defender för slutpunkt, Windows Defender, Windows Defender ATP, Windows Defender Avancerat skydd, sökning, fråga, telemetri, schemareferens, kusto, FileProfile, filprofil, funktion, vinst
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 5dcc41302d797b4084c36d020908ba59131c90d4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499278"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="b572d-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="b572d-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

><span data-ttu-id="b572d-105">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b572d-105">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b572d-106">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b572d-106">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="b572d-107">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b572d-107">**Applies to:**</span></span>
- [<span data-ttu-id="b572d-108">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b572d-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="b572d-109">Använd funktionen `AssignedIPAddresses()` för avancerade sökfrågor för att snabbt hämta de senaste IP-adresserna som har tilldelats till en enhet.</span><span class="sxs-lookup"><span data-stu-id="b572d-109">Use the `AssignedIPAddresses()` function in your advanced hunting queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="b572d-110">Om du anger ett tidsstämpelargument hämtar den här funktionen de senaste IP-adresserna vid den angivna tiden.</span><span class="sxs-lookup"><span data-stu-id="b572d-110">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span>

<span data-ttu-id="b572d-111">Den här funktionen returnerar en tabell med följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="b572d-111">This function returns a table with the following columns:</span></span>

<span data-ttu-id="b572d-112">Kolumn</span><span class="sxs-lookup"><span data-stu-id="b572d-112">Column</span></span> | <span data-ttu-id="b572d-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="b572d-113">Data type</span></span> | <span data-ttu-id="b572d-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b572d-114">Description</span></span>
-|-|-
`Timestamp` | <span data-ttu-id="b572d-115">datetime</span><span class="sxs-lookup"><span data-stu-id="b572d-115">datetime</span></span> | <span data-ttu-id="b572d-116">Senaste gången då enheten observerades med HJÄLP av IP-adressen</span><span class="sxs-lookup"><span data-stu-id="b572d-116">Latest time when the device was observed using the IP address</span></span>
`IPAddress` | <span data-ttu-id="b572d-117">sträng</span><span class="sxs-lookup"><span data-stu-id="b572d-117">string</span></span> | <span data-ttu-id="b572d-118">IP-adress som används av enheten</span><span class="sxs-lookup"><span data-stu-id="b572d-118">IP address used by the device</span></span>
`IPType` | <span data-ttu-id="b572d-119">sträng</span><span class="sxs-lookup"><span data-stu-id="b572d-119">string</span></span> | <span data-ttu-id="b572d-120">Anger om IP-adressen är en offentlig eller privat adress</span><span class="sxs-lookup"><span data-stu-id="b572d-120">Indicates whether the IP address is a public or private address</span></span>
`NetworkAdapterType` | <span data-ttu-id="b572d-121">int</span><span class="sxs-lookup"><span data-stu-id="b572d-121">int</span></span> | <span data-ttu-id="b572d-122">Nätverksadaptertyp som används av enheten som har tilldelats IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="b572d-122">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="b572d-123">Information om möjliga värden finns i [denna uppräkning](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="b572d-123">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span>
`ConnectedNetworks` | <span data-ttu-id="b572d-124">int</span><span class="sxs-lookup"><span data-stu-id="b572d-124">int</span></span> | <span data-ttu-id="b572d-125">Nätverk som adaptern med den tilldelade IP-adressen är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="b572d-125">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="b572d-126">Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet</span><span class="sxs-lookup"><span data-stu-id="b572d-126">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span>

## <a name="syntax"></a><span data-ttu-id="b572d-127">Syntax</span><span class="sxs-lookup"><span data-stu-id="b572d-127">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="b572d-128">Argument</span><span class="sxs-lookup"><span data-stu-id="b572d-128">Arguments</span></span>

- <span data-ttu-id="b572d-129">**x**– `DeviceId` eller värde som identifierar `DeviceName` enheten</span><span class="sxs-lookup"><span data-stu-id="b572d-129">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="b572d-130">**y**– (datetime)-värde som instruerar funktionen för att hämta de senast tilldelade `Timestamp` IP-adresserna från en viss tid.</span><span class="sxs-lookup"><span data-stu-id="b572d-130">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="b572d-131">Om detta inte anges returnerar funktionen de senaste IP-adresserna.</span><span class="sxs-lookup"><span data-stu-id="b572d-131">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="b572d-132">Exempel</span><span class="sxs-lookup"><span data-stu-id="b572d-132">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="b572d-133">Hämta listan med IP-adresser som användes av en enhet för 24 timmar sedan</span><span class="sxs-lookup"><span data-stu-id="b572d-133">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="b572d-134">Få IP-adresser använda av en enhet och hitta enheter som kommunicerar med den</span><span class="sxs-lookup"><span data-stu-id="b572d-134">Get IP addresses used by a device and find devices communicating with it</span></span>

<span data-ttu-id="b572d-135">Den här frågan använder `AssignedIPAddresses()` funktionen för att hämta tilldelade IP-adresser för enheten `example-device-name` () på eller före ett visst datum ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="b572d-135">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="b572d-136">Därefter används IP-adresserna för att hitta anslutningar till enheten initierad av andra enheter.</span><span class="sxs-lookup"><span data-stu-id="b572d-136">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="b572d-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b572d-137">Related topics</span></span>

- [<span data-ttu-id="b572d-138">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="b572d-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b572d-139">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="b572d-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b572d-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="b572d-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
