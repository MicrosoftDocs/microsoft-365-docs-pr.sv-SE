---
title: Funktionen DeviceFromIP() i avancerad sökning efter Microsoft 365 Defender
description: Lär dig hur du använder funktionen DeviceFromIP() för att få de enheter som har tilldelats en specifik IP-adress
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function,richment
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
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933187"
---
# <a name="devicefromip"></a><span data-ttu-id="751d2-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="751d2-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="751d2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="751d2-105">**Applies to:**</span></span>
- <span data-ttu-id="751d2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="751d2-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="751d2-107">Använd funktionen i dina avancerade sökfrågor för att snabbt hämta listan över enheter som har tilldelats en `DeviceFromIP()` viss IP-adress vid en viss tidpunkt. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="751d2-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="751d2-108">Den här funktionen returnerar en tabell med följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="751d2-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="751d2-109">Kolumn</span><span class="sxs-lookup"><span data-stu-id="751d2-109">Column</span></span> | <span data-ttu-id="751d2-110">Datatyp</span><span class="sxs-lookup"><span data-stu-id="751d2-110">Data type</span></span> | <span data-ttu-id="751d2-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="751d2-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="751d2-112">sträng</span><span class="sxs-lookup"><span data-stu-id="751d2-112">string</span></span> | <span data-ttu-id="751d2-113">IP-adress</span><span class="sxs-lookup"><span data-stu-id="751d2-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="751d2-114">sträng</span><span class="sxs-lookup"><span data-stu-id="751d2-114">string</span></span> | <span data-ttu-id="751d2-115">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="751d2-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="751d2-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="751d2-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="751d2-117">Argument</span><span class="sxs-lookup"><span data-stu-id="751d2-117">Arguments</span></span>

<span data-ttu-id="751d2-118">Den här funktionen anropas som en del av en fråga.</span><span class="sxs-lookup"><span data-stu-id="751d2-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="751d2-119">**x**– Den första parametern är vanligtvis redan en kolumn i frågan.</span><span class="sxs-lookup"><span data-stu-id="751d2-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="751d2-120">I det här fallet är det kolumnen med namnet , IP-adressen som du vill se en lista med enheter `IP` som har tilldelats till den.</span><span class="sxs-lookup"><span data-stu-id="751d2-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="751d2-121">Det ska vara en lokal IP-adress.</span><span class="sxs-lookup"><span data-stu-id="751d2-121">It should be a local IP address.</span></span> <span data-ttu-id="751d2-122">Externa IP-adresser stöds inte.</span><span class="sxs-lookup"><span data-stu-id="751d2-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="751d2-123">**y**– En andra valfri parameter är , som instruerar funktionen för att hämta de senast tilldelade enheterna `Timestamp` från en viss tid.</span><span class="sxs-lookup"><span data-stu-id="751d2-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="751d2-124">Om den inte anges returnerar funktionen de senaste tillgängliga posterna.</span><span class="sxs-lookup"><span data-stu-id="751d2-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="751d2-125">Exempel</span><span class="sxs-lookup"><span data-stu-id="751d2-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="751d2-126">Hämta de senaste enheterna som har tilldelats specifika IP-adresser</span><span class="sxs-lookup"><span data-stu-id="751d2-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="751d2-127">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="751d2-127">Related topics</span></span>
- [<span data-ttu-id="751d2-128">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="751d2-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="751d2-129">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="751d2-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="751d2-130">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="751d2-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
