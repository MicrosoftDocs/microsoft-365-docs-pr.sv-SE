---
title: DeviceNetworkInfo-tabell i det avancerade sökschemat
description: Mer information om nätverkskonfiguration finns i tabellen DeviceNetworkInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicenetworkinfo, device, device, mac, ip, adapter, dns, gateway, tunnel, DeviceNetworkInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ba3e81163cdbba54bf718dca929e2df3b39a1c3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075090"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="559b9-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="559b9-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="559b9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="559b9-105">**Applies to:**</span></span>
- [<span data-ttu-id="559b9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="559b9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="559b9-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="559b9-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="559b9-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="559b9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="559b9-109">Tabellen i det avancerade sökschemat innehåller information om nätverkskonfiguration av enheter, t.ex. `DeviceNetworkInfo` nätverkskort, IP- och MAC-adresser och anslutna nätverk eller domäner. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="559b9-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="559b9-110">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="559b9-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="559b9-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="559b9-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="559b9-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="559b9-112">Column name</span></span> | <span data-ttu-id="559b9-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="559b9-113">Data type</span></span> | <span data-ttu-id="559b9-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="559b9-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="559b9-115">datetime</span><span class="sxs-lookup"><span data-stu-id="559b9-115">datetime</span></span> | <span data-ttu-id="559b9-116">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="559b9-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="559b9-117">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-117">string</span></span> | <span data-ttu-id="559b9-118">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="559b9-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="559b9-119">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-119">string</span></span> | <span data-ttu-id="559b9-120">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="559b9-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="559b9-121">long</span><span class="sxs-lookup"><span data-stu-id="559b9-121">long</span></span> | <span data-ttu-id="559b9-122">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="559b9-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="559b9-123">För att identifiera unika händelser måste den här kolumnen användas tillsammans med `DeviceName` `Timestamp` kolumnerna och</span><span class="sxs-lookup"><span data-stu-id="559b9-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="559b9-124">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-124">string</span></span> | <span data-ttu-id="559b9-125">Namn på nätverksadaptern</span><span class="sxs-lookup"><span data-stu-id="559b9-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="559b9-126">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-126">string</span></span> | <span data-ttu-id="559b9-127">MAC-adressen för nätverksadaptern</span><span class="sxs-lookup"><span data-stu-id="559b9-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="559b9-128">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-128">string</span></span> | <span data-ttu-id="559b9-129">Nätverksadaptertyp.</span><span class="sxs-lookup"><span data-stu-id="559b9-129">Network adapter type.</span></span> <span data-ttu-id="559b9-130">Information om möjliga värden finns i [denna uppräkning](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="559b9-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="559b9-131">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-131">string</span></span> | <span data-ttu-id="559b9-132">Driftstatus för nätverksadaptern.</span><span class="sxs-lookup"><span data-stu-id="559b9-132">Operational status of the network adapter.</span></span> <span data-ttu-id="559b9-133">Information om möjliga värden finns i [denna uppräkning](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="559b9-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="559b9-134">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-134">string</span></span> | <span data-ttu-id="559b9-135">Tunnelprotokoll, om gränssnittet används för detta ändamål, t.ex. 6to4, Det här exemplet För företag, ISATAP, PPTP, SSTP och SSH</span><span class="sxs-lookup"><span data-stu-id="559b9-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="559b9-136">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-136">string</span></span> | <span data-ttu-id="559b9-137">Nätverk som adaptern är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="559b9-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="559b9-138">Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet</span><span class="sxs-lookup"><span data-stu-id="559b9-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="559b9-139">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-139">string</span></span> | <span data-ttu-id="559b9-140">DNS-serveradresser i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="559b9-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="559b9-141">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-141">string</span></span> | <span data-ttu-id="559b9-142">IPv4-adressen till PSP-servern</span><span class="sxs-lookup"><span data-stu-id="559b9-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="559b9-143">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-143">string</span></span> | <span data-ttu-id="559b9-144">IPv6-adressen till PSP-servern</span><span class="sxs-lookup"><span data-stu-id="559b9-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="559b9-145">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-145">string</span></span> | <span data-ttu-id="559b9-146">Standardgatewayadresser i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="559b9-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="559b9-147">sträng</span><span class="sxs-lookup"><span data-stu-id="559b9-147">string</span></span> | <span data-ttu-id="559b9-148">JSON-matris som innehåller alla IP-adresser som tilldelats adaptern, tillsammans med respektive undernätsprefix och IP-adressutrymme, t.ex. offentlig, privat eller länk lokalt</span><span class="sxs-lookup"><span data-stu-id="559b9-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="559b9-149">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="559b9-149">Related topics</span></span>
- [<span data-ttu-id="559b9-150">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="559b9-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="559b9-151">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="559b9-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="559b9-152">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="559b9-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
