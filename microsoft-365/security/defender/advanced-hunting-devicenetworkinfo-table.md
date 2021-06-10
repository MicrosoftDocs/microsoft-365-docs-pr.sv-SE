---
title: DeviceNetworkInfo-tabell i det avancerade sökschemat
description: Mer information om nätverkskonfiguration finns i tabellen DeviceNetworkInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, gateway, tunnel
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
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023199"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="54867-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="54867-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="54867-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="54867-105">**Applies to:**</span></span>
- <span data-ttu-id="54867-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54867-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="54867-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="54867-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="54867-108">Tabellen `DeviceNetworkInfo` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om nätverkskonfiguration av maskiner, inklusive nätverkskort, IP- och MAC-adresser och anslutna nätverk eller domäner.</span><span class="sxs-lookup"><span data-stu-id="54867-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="54867-109">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="54867-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="54867-110">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="54867-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="54867-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="54867-111">Column name</span></span> | <span data-ttu-id="54867-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="54867-112">Data type</span></span> | <span data-ttu-id="54867-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="54867-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="54867-114">datetime</span><span class="sxs-lookup"><span data-stu-id="54867-114">datetime</span></span> | <span data-ttu-id="54867-115">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="54867-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="54867-116">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-116">string</span></span> | <span data-ttu-id="54867-117">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="54867-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="54867-118">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-118">string</span></span> | <span data-ttu-id="54867-119">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="54867-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="54867-120">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-120">string</span></span> | <span data-ttu-id="54867-121">Namn på nätverksadaptern</span><span class="sxs-lookup"><span data-stu-id="54867-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="54867-122">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-122">string</span></span> | <span data-ttu-id="54867-123">MAC-adressen för nätverksadaptern</span><span class="sxs-lookup"><span data-stu-id="54867-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="54867-124">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-124">string</span></span> | <span data-ttu-id="54867-125">Nätverksadaptertyp.</span><span class="sxs-lookup"><span data-stu-id="54867-125">Network adapter type.</span></span> <span data-ttu-id="54867-126">Information om möjliga värden finns i [denna uppräkning](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="54867-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="54867-127">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-127">string</span></span> | <span data-ttu-id="54867-128">Driftstatus för nätverksadaptern.</span><span class="sxs-lookup"><span data-stu-id="54867-128">Operational status of the network adapter.</span></span> <span data-ttu-id="54867-129">Information om möjliga värden finns i [denna uppräkning](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="54867-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="54867-130">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-130">string</span></span> | <span data-ttu-id="54867-131">Tunnelprotokoll, om gränssnittet används för detta ändamål, t.ex. 6to4, Det här exemplet För företag, ISATAP, PPTP, SSTP och SSH</span><span class="sxs-lookup"><span data-stu-id="54867-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="54867-132">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-132">string</span></span> | <span data-ttu-id="54867-133">Nätverk som adaptern är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="54867-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="54867-134">Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet</span><span class="sxs-lookup"><span data-stu-id="54867-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="54867-135">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-135">string</span></span> | <span data-ttu-id="54867-136">DNS-serveradresser i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="54867-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="54867-137">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-137">string</span></span> | <span data-ttu-id="54867-138">IPv4-adressen till PSP-servern</span><span class="sxs-lookup"><span data-stu-id="54867-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="54867-139">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-139">string</span></span> | <span data-ttu-id="54867-140">IPv6-adressen till PSP-servern</span><span class="sxs-lookup"><span data-stu-id="54867-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="54867-141">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-141">string</span></span> | <span data-ttu-id="54867-142">Standardgatewayadresser i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="54867-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="54867-143">sträng</span><span class="sxs-lookup"><span data-stu-id="54867-143">string</span></span> | <span data-ttu-id="54867-144">JSON-matris som innehåller alla IP-adresser som tilldelats adaptern, tillsammans med respektive undernätsprefix och IP-adressutrymme, t.ex. offentlig, privat eller länk lokalt</span><span class="sxs-lookup"><span data-stu-id="54867-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="54867-145">long</span><span class="sxs-lookup"><span data-stu-id="54867-145">long</span></span> | <span data-ttu-id="54867-146">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="54867-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="54867-147">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="54867-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="54867-148">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="54867-148">Related topics</span></span>
- [<span data-ttu-id="54867-149">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="54867-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="54867-150">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="54867-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="54867-151">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="54867-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="54867-152">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="54867-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="54867-153">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="54867-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="54867-154">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="54867-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)