---
title: Funktionen DeviceFromIP() i avancerad sökning för Microsoft 365 Defender
description: Lär dig hur du använder funktionen DeviceFromIP() för att få enheter som har tilldelats en specifik IP-adress
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, enhet, devicefromIP, funktion, vinst
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931308"
---
# <a name="devicefromip"></a><span data-ttu-id="b5f40-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="b5f40-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b5f40-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b5f40-105">**Applies to:**</span></span>
- <span data-ttu-id="b5f40-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5f40-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="b5f40-107">Använd funktionen i dina avancerade sökningsfrågor för att snabbt hämta listan över enheter som har tilldelats till en viss `DeviceFromIP()` IP-adress vid en [](advanced-hunting-overview.md) viss tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="b5f40-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="b5f40-108">Den här funktionen returnerar en tabell med följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="b5f40-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="b5f40-109">Kolumn</span><span class="sxs-lookup"><span data-stu-id="b5f40-109">Column</span></span> | <span data-ttu-id="b5f40-110">Datatyp</span><span class="sxs-lookup"><span data-stu-id="b5f40-110">Data type</span></span> | <span data-ttu-id="b5f40-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b5f40-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="b5f40-112">sträng</span><span class="sxs-lookup"><span data-stu-id="b5f40-112">string</span></span> | <span data-ttu-id="b5f40-113">IP-adress</span><span class="sxs-lookup"><span data-stu-id="b5f40-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="b5f40-114">sträng</span><span class="sxs-lookup"><span data-stu-id="b5f40-114">string</span></span> | <span data-ttu-id="b5f40-115">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="b5f40-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="b5f40-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5f40-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="b5f40-117">Argument</span><span class="sxs-lookup"><span data-stu-id="b5f40-117">Arguments</span></span>

<span data-ttu-id="b5f40-118">Den här funktionen anropas som en del av en fråga.</span><span class="sxs-lookup"><span data-stu-id="b5f40-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="b5f40-119">**x**– Den första parametern är vanligtvis redan en kolumn i frågan.</span><span class="sxs-lookup"><span data-stu-id="b5f40-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="b5f40-120">I det här fallet är det kolumnen med namnet , IP-adressen som du vill se en lista med `IP` enheter som har tilldelats till den.</span><span class="sxs-lookup"><span data-stu-id="b5f40-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="b5f40-121">Det ska vara en lokal IP-adress.</span><span class="sxs-lookup"><span data-stu-id="b5f40-121">It should be a local IP address.</span></span> <span data-ttu-id="b5f40-122">Externa IP-adresser stöds inte.</span><span class="sxs-lookup"><span data-stu-id="b5f40-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="b5f40-123">**y**– En andra valfri parameter är den som instruerar funktionen att hämta de senaste tilldelade enheterna `Timestamp` från en viss tid.</span><span class="sxs-lookup"><span data-stu-id="b5f40-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="b5f40-124">Om den inte anges returnerar funktionen de senaste tillgängliga posterna.</span><span class="sxs-lookup"><span data-stu-id="b5f40-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="b5f40-125">Exempel</span><span class="sxs-lookup"><span data-stu-id="b5f40-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="b5f40-126">Hämta de senaste enheterna som har tilldelats specifika IP-adresser</span><span class="sxs-lookup"><span data-stu-id="b5f40-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="b5f40-127">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b5f40-127">Related topics</span></span>
- [<span data-ttu-id="b5f40-128">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="b5f40-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b5f40-129">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="b5f40-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b5f40-130">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="b5f40-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
