---
title: DeviceFromIP ()-funktion i avancerad jakt för Microsoft 365 Defender
description: Lär dig hur du använder funktionen DeviceFromIP () för att hämta enheter som har tilldelats en viss IP-adress
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, enhet, devicefromIP, funktion och berikning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741118"
---
# <a name="devicefromip"></a><span data-ttu-id="07b76-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="07b76-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="07b76-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="07b76-105">**Applies to:**</span></span>
- <span data-ttu-id="07b76-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07b76-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="07b76-107">Använd `DeviceFromIP()` funktionen i de [avancerade jakt](advanced-hunting-overview.md) frågorna för att snabbt få reda på listan med enheter som har tilldelats en viss IP-adress vid en viss tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="07b76-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="07b76-108">Den här funktionen returnerar en tabell med följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="07b76-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="07b76-109">Kolumn</span><span class="sxs-lookup"><span data-stu-id="07b76-109">Column</span></span> | <span data-ttu-id="07b76-110">Datatyp</span><span class="sxs-lookup"><span data-stu-id="07b76-110">Data type</span></span> | <span data-ttu-id="07b76-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="07b76-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="07b76-112">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="07b76-112">string</span></span> | <span data-ttu-id="07b76-113">IP-adress</span><span class="sxs-lookup"><span data-stu-id="07b76-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="07b76-114">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="07b76-114">string</span></span> | <span data-ttu-id="07b76-115">Unik identifierare för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="07b76-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="07b76-116">Frågesyntaxen</span><span class="sxs-lookup"><span data-stu-id="07b76-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="07b76-117">Argument</span><span class="sxs-lookup"><span data-stu-id="07b76-117">Arguments</span></span>

<span data-ttu-id="07b76-118">Den här funktionen anropas som en del av en fråga.</span><span class="sxs-lookup"><span data-stu-id="07b76-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="07b76-119">**x**– den första parametern är oftast redan en kolumn i frågan.</span><span class="sxs-lookup"><span data-stu-id="07b76-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="07b76-120">I det här fallet är det kolumnen som heter `IP` , den IP-adress som du vill visa en lista över enheter som har tilldelats till den.</span><span class="sxs-lookup"><span data-stu-id="07b76-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="07b76-121">Det ska vara en lokal IP-adress.</span><span class="sxs-lookup"><span data-stu-id="07b76-121">It should be a local IP address.</span></span> <span data-ttu-id="07b76-122">Externa IP-adresser stöds inte.</span><span class="sxs-lookup"><span data-stu-id="07b76-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="07b76-123">**y**– en andra valfri parameter är den `Timestamp` som används för att hämta de senaste tilldelade enheterna från en viss tid.</span><span class="sxs-lookup"><span data-stu-id="07b76-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="07b76-124">Om det inte anges returnerar funktionen de senaste tillgängliga posterna.</span><span class="sxs-lookup"><span data-stu-id="07b76-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="07b76-125">Exempel</span><span class="sxs-lookup"><span data-stu-id="07b76-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="07b76-126">Skaffa de senaste enheterna som har tilldelats särskilda IP-adresser</span><span class="sxs-lookup"><span data-stu-id="07b76-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="07b76-127">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="07b76-127">Related topics</span></span>
- [<span data-ttu-id="07b76-128">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="07b76-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="07b76-129">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="07b76-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="07b76-130">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="07b76-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
